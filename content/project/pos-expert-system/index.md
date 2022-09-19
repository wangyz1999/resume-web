---
title: Fixing Chinese Part-of-Speech Tagging Errors
subtitle: Automatically corrects POS tagging errors using an rule-based expert system
summary: Automatically corrects POS tagging errors using an rule-based expert system
tags:
- Academic
- Natural Language Processing
date: "2019-08-16T00:00:00Z"
lastmod: "2019-08-16T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Example rules and fixes of my rule-based system
  focal_point: Smart

links:
url_code: "https://github.com/wangyz1999/pku_pos_modifier"
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

Part-of-speech (POS) tagging is a fundamental NLP research task that categorizes words in a text (corpus) in correspondence with a particular part of speech, depending on the word's definition and context. The marked POS tags can be used as augmented features and be further used for model improvement or downstream analysis. Here is an example of part of speech tagging in both English and Chinese.

```
I/prp am/v a/dt college/n student/n
我/prp 是/v 一名/dt 大学生/n
```

Most part-of-speech tagging systems are based on the Hidden Markov Model and trained on a labeled corpus. For the Chinese POS tagging, publicly available state-of-the-art models include the [Stanford CoreNLP](https://stanfordnlp.github.io/CoreNLP/index.html) model and the [NLPIR-ICTCLAS](http://ictclas.nlpir.org/index_e.html) tagging system. Nonetheless, as these models were data-driven and modeled the tagging based on probability, errors are inevitable even if the POS rule is well defined. 

To tackle this problem, we developed a rule-based expert system that iteratively modifies tagged POS after existing models have already assigned the POS. This way, the trained model can give a baseline POS assignment difficult for a rule-based system to do. The accuracy can be improved using grammatical rules that the trained model could occasionally make mistakes, but rule-based systems will deterministically fix the error.

In artificial intelligence, an expert system is a computer system emulating the decision-making ability of a human expert. Expert systems are designed to solve complex problems by reasoning through bodies of knowledge, represented mainly as if-then rules. An example rule in our system looks like this:

```
KEY多/a+了/u+解下/v->[多/a 了/u 解下/v]MERGE[多/d 了解/v 下/f]
```

Which will change the sentence tokenization and POS tagging from

```
感/v 兴趣/n 的/u 朋友/n 不妨/d 多/a 了/u 解下/v
```
To

```
感/v 兴趣/n 的/u 朋友/n 不妨/d 多/d 了解/v 下/f
```

Notice that the trained HMM mistakenly tokenizes and tags the phrase `了解下` as `了/u 解下/v`, whereas the correct assignment should be `了解/v 下/f`. More descriptions about correction rules can be found on the [Github repo](https://github.com/wangyz1999/pku_pos_modifier). After handcrafting around 300 rules based on human knowledge, we discovered that this rule-based system could already improve the POS tagging accuracy in many cases. Nonetheless, handcrafted rules require lots of human error. An interesting question is: how can we automatically discover rules directly from the data?

Having this question in mind, in some cases, different POS tagging models could make drastically different decisions. Specifically, I ran the Stanford CoreNLP model and the NLPIR-ICTCLAS model on the same corpus and studied the similarity and differences between their outputs. Given the same sentence, if the tokenizing and POS tagging results for the two systems are different, it generally falls into four categories:

1. Tagging system A outputs the same tagging result in most cases (high confidence in system A), while tagging system B equivocally outputs different tagging results in most cases (low confidence in system B)
2. Tagging system B outputs the same tagging result in most cases (high confidence in system B), while tagging system A equivocally output different tagging result in most cases (low confidence in system A)
3. Both tagging system A and B outputs the same tagging result in most cases, but their output is different (high conflict)
4. Both tagging system A and B outputs different tagging results in most cases (equivocal case).

After identifying the difference between the two systems, we quickly discovered over 2000 more rules. In most cases, the tagging system that is more confident/deterministic about a particular case (category 1 and 2) makes the correct tagging decision. Category 3 requires a closer expert inspection to judge which system makes the right decision. Differences that fall into category 4 are the rarest but most difficult to fix as a human rule targeting this category might often unexpectedly cause errors in tagging decisions that were previously made correctly.

