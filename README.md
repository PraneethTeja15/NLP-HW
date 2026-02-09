# NLP-HW
# CS5760 – Natural Language Processing

## Homework 1 – Q5 Programming: Tokenization Comparison

**Student Name:** Jilkapally Praneeth Teja
**Course:** CS5760 Natural Language Processing
**Semester:** Spring 2026
**University:** University of Central Missouri

---

# Overview

This program demonstrates different approaches to tokenization in Natural Language Processing (NLP). Tokenization is the process of breaking text into smaller units called tokens. In this assignment, I performed naïve tokenization, manual token correction, and compared the results with an NLP tool (NLTK tokenizer). The goal is to understand how punctuation, clitics, and multiword expressions affect tokenization.

---

# Paragraph Used

The following paragraph was used for tokenization:

> NLP is transforming the world. It's used in chatbots, translation, and search engines. Many students don't realize how powerful language models are. Today, AI-driven tools are everywhere.

---

# 1. Tokenization Approaches

## Naïve Space-Based Tokenization

Naïve tokenization splits text based only on spaces using Python's `split()` function. This method is simple but inaccurate because punctuation and contractions remain attached to words.

Example output:

* "world." remains attached to period
* "chatbots," remains attached to comma
* "It's" and "don't" are not separated correctly

This approach does not handle punctuation, suffixes, or clitics.

---

## Manual Tokenization (Corrected)

Manual tokenization was performed to properly separate:

* punctuation marks (., , !)
* contractions (It's → It + 's, don't → do + n't)
* hyphenated words (AI-driven → AI + - + driven)

This produces linguistically accurate tokens suitable for NLP tasks.

Manual tokenization improves:

* sentence structure recognition
* morphological understanding
* downstream NLP model performance

---

# 2. Comparison with NLP Tool (NLTK)

The paragraph was processed using the NLTK tokenizer (`word_tokenize`).
NLTK automatically handles punctuation and most contractions.

## Observed Differences

* NLTK keeps some hyphenated words together (AI-driven)
* Manual tokenization splits hyphen explicitly (AI - driven)
* Both handle contractions like "don't" correctly
* Both separate punctuation properly

## Why Differences Occur

NLP tools follow predefined linguistic rules and tokenization standards.
Manual tokenization depends on user-defined choices. Some tools treat hyphenated words as single tokens to preserve meaning.

---

# 3. Multiword Expressions (MWEs)

Multiword expressions are phrases that function as a single semantic unit.

Examples:

1. Natural Language Processing
2. Machine Learning
3. New York

These should be treated as single tokens because:

* splitting them changes meaning
* they represent single concepts
* improves NLP model accuracy

Handling MWEs correctly helps in tasks like machine translation, information retrieval, and sentiment analysis.

---

# 4. Reflection

The hardest part of tokenization in English is handling contractions, punctuation, and hyphenated words correctly. Words like "don't" and "AI-driven" require special rules to tokenize properly. Compared to some languages, English tokenization is easier because spaces clearly separate words. However, punctuation and clitics still create challenges for naïve tokenization. Multiword expressions also increase complexity because multiple words can represent a single meaning. Overall, punctuation, morphology, and MWEs make tokenization more complex and require careful handling for accurate NLP processing.

---

# How to Run the Program

## Requirements

* Python 3.x
* NLTK library

## Install NLTK

Run:

```
pip install nltk
```

## Run the Program

```
python tokenization_q5.py
```

The program will display:

* original paragraph
* naïve tokens
* manually corrected tokens
* NLTK tokenization
* differences between tokens

---

# Conclusion

This assignment demonstrates the importance of proper tokenization in NLP. Naïve tokenization is simple but inaccurate, while manual and tool-based tokenization provide more linguistically correct results. Handling punctuation, clitics, and multiword expressions significantly improves token quality and downstream NLP performance.
