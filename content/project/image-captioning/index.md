---
title: Image Captioning with Conditioned LSTM Generators
summary: Generate text descriptions to a given image using LSTM neural network
tags:
- Academic
- Computer Vision
- Natural Language Processing
date: "2021-12-04T00:00:00Z"
lastmod: "2021-12-04T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Captioning image using neural network language model
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---


Image Captioning is the task of describing the content of an image in words. This task lies at the intersection of computer vision and natural language processing. Most image captioning systems use an encoder-decoder framework, where an input image is encoded into an intermediate representation of the information in the image, and then decoded into a descriptive text sequence. 

In this project, I used an off-the-shelf pre-trained image encoder, the [Inception V3](https://arxiv.org/abs/1512.00567) network as the image encoder. I then decode the meaning of the image using an LSTM network, which autoregressively predicts the next word given a partial input sequence. The image description dataset I used is the [flickr8k dataset](https://www.ijcai.org/Proceedings/15/Papers/593.pdf). To obtain diverse text descriptions, I implemented a greedy decoder, a probabilistic decoder, a nucleus sampling decoder, and a beam search decoder. The quality of the decoded text was then evaluated using the BLEU score.

### Obtaining Image Representation

Inception-v3 is a convolutional neural network architecture from the Inception family that makes several improvements including using Label Smoothing, Factorized 7 x 7 convolutions, and the use of an auxiliary classifier to propagate label information lower down the network. By taking in a 3-color channel 299x299 image, the inception-v3 network outputs a softmax-activated vector representing 1000 possible object types. Because we are interested in an encoded representation of the image we only use the second-to-last layer as a source of image encodings. Each image will be encoded as a vector of size 2048.

### Text Generation Conditioned on Images

| i | input (partial sequence)     | output (next word) |
|---|------------------------------|--------|
| 0 |[`START`]                     | `a`    |  
| 1 |[`START`,`a`]                 | `black`|
| 2 |[`START`,`a`, `black`]        | `dog`  |
| 3 |[`START`,`a`, `black`, `dog`] | `.`  |
| 3 |[`START`,`a`, `black`, `dog`, `.`] | `END`  |

To generate text captions, we structured our input as partial sequences while outputting the probability of the next word. For example, given the partial sequence ["START", "a"], the model might predict "dog" as the most likely next word. I used a bidirectional LSTM network to encode the partial sequence. Since the caption needs to explain a corresponding image, I concatenate the image embedding together with the partial sequence embedding as the input to LSTM. The output next word will be auto-regressively appended back to the partial sequence. The process repeats until the “END” token is reached.

![Model Architecture](https://raw.githubusercontent.com/yunjey/pytorch-tutorial/master/tutorials/03-advanced/image_captioning/png/model.png "Images are first encoded into a representation vector through pretrained Inception-v3 net, and then decoded using an LSTM network")


### Decoding Text

By design, the last layer output of the LSTM network is then fed into a fully connected layer and softmax activated. The output result, therefore, represents the probability distribution of the word over the entire vocabulary. A greedy decoding approach is to always choose the word with max probability at each step, but there were two limitations. First, a sentence consisting of words with the highest word probability at each step doesn’t necessarily produce the sentence with the highest sentence probability, since the next word distribution is conditioned on the previous word. Second, this doesn’t give enough variations in the decoded sequence, and the generated text tends to be stale and not descriptive enough. 

To address the first issue, instead of always selecting the most probable word, I use the [Beam Search](https://en.wikipedia.org/wiki/Beam_search), which contains the n highest-scoring sequences so far and their total probability (i.e. the product of all word probabilities). After each time step, I prune the list to include only the n most probable sequences. Then, for each sequence, compute the n most likely successor words. Append the word to produce n new sequences and compute their score. This way, I create a new list of n*n candidates. The entire process can be optimized by maintaining a priority queue with n elements. Since the greedy decoding is essentially one of the beams that we are maintaining, the sentence output by beam search will have a probability strictly higher than that found by the greedy search.

To address the second issue and make the decoding text more interesting, I also attempted a probabilistic approach, which samples the next word given the softmax probability distribution. Nonetheless, this approach may end up choosing rare words with a pretty high chance that the decoder failed to finish the sentence gracefully. The phenomenon is explainable by [Zipf’s law](https://en.wikipedia.org/wiki/Zipf%27s_law). An improved probabilistic decoding approach is the [Nucleus Sampling (Holtzman, 2019)](https://arxiv.org/abs/1904.09751). Rather than sampling from the entire vocabulary distribution, we only consider the smallest subset of the vocabulary tokens whose cumulative probability mass reaches a predefined threshold p (the "nucleus" of the distribution). The probability mass of truncated tokens is then redistributed to the selected tokens. We sample the next word from this re-normalized truncated distribution. This prevents the model to select rare words which makes it difficult to finish the sentence.

![Decoding Image](baseball.jpg "Examples of Deocded Text from the baseball image is shown in the table below. Text are decoded using Beam Saerch with differernt n parameter and the probabilistic nucleus sampling approach with 5 different trials")

| Method | Decoded Text     | 
|------------------|------------------------------|
| Beam Search n=1  | A baseball player swings his bat to catch the ball.                     |
| Beam Search n=3  | A man playing baseball.                 |
| Beam Search n=5  | The baseball player swings the bat.        |
| Beam Search n=10 | The boy is playing baseball. |
| Beam Search n=20 | The man is playing baseball. |
| Nucleus Sampling  | A football player runs with the ball in a race. |
| Nucleus Sampling  | Three man, are in a race, and two teammates kicking the football. |
| Nucleus Sampling  | The batsman playing football.        |
| Nucleus Sampling  | A group of girls in blue play soccer game. |
| Nucleus Sampling  | A lacross player runs after a ball. |

### BLEU Score Evaluation

Finally, the trained model is evaluated on our development set using a standard evaluation metric in language generation tasks: [BiLingual Evaluation Understudy (BLEU)](https://en.wikipedia.org/wiki/BLEU). The BLEU score is a number between zero and one that measures the similarity of the machine-translated text to a set of high-quality reference translations. A value of 0 means that the machine-translated output has no overlap with the reference translation (low quality) while a value of 1 means there is perfect overlap with the reference translations (high quality). The table below show the BLEU score evaluation of different decoding method on the test dataset.

| Method | BLEU Score |
|---------|-----------|
| Greedy | 0.331 |
| Beam Search n=3 | 0.347 |
| Beam Search n=5 | 0.351 |
| Nucleus Sampling | 0.281 |

