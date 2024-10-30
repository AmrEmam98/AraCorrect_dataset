# Syntactic Dataset with Noisy Text Generation

This dataset includes syntactically noisy text generated from a base corpus of **5 million+ correct sentences**. The dataset was created by applying a variety of noise-inducing algorithms to simulate common linguistic errors, such as spelling mistakes, segmentation errors, context errors, and grammatical inaccuracies.

## Dataset Overview

The dataset comprises two main components:
1. **Original Sentences:** Correctly constructed sentences, forming the base corpus.
2. **Noisy Sentences:** Sentences with syntactic noise applied based on specific noise algorithms, mimicking typical user errors in written language.

## Types of Noise Applied

### 1. Spelling Noise
Spelling noise introduces common spelling mistakes by altering characters within random words. The following transformations are applied:
- **Adding Characters:** Adds a random character at a random index within a random word.
- **Removing Characters:** Removes a character at a random index within a random word.
- **Replacing Similar Characters:** Replaces a character with a visually similar one. For example:
  - Arabic characters: (ح, ج, خ) or (م, ه)

### 2. Segmentation Noise
Segmentation noise affects the spacing between words, which can alter word boundaries:
- **Insert Space:** Inserts a space at a random position within a word.
- **Remove Space:** Deletes the space between a word and the next word.

### 3. Grammar Noise
Grammar noise modifies verbs in a sentence to create grammatical errors:
- **Verb Lemmatization:** Detects all verbs in a sentence and extracts their lemmas.
- **Verb Variations:** Uses the `libqutrub` package to generate variations of each verb. For example:
  - The verb (لعب) may produce forms like (لعب, يلعب, تلعب, لعبن, يلعبن).
- **Replace with Variants:** Replaces a verb in the sentence with a randomly selected variation.

### 4. Context Noise
Context noise replaces words with similar words based on context:
- **Identify Similar Words:** For each word, retrieve a list of words with a similarity score >80.
- **Random Replacement:** Replace the original word with a random one from the list of similar words.

## Noise Application Proportion

Each type of noise is applied to a specific portion of the dataset:
| Noise Type           | Portion of Dataset |
|----------------------|--------------------|
| Spelling Noise       | 20%                |
| Segmentation Noise   | 10%                |
| Grammar Noise        | 5%                 |
| Context Noise        | 5%                 |

## Usage

This syntactic dataset is useful for training machine learning models in text processing tasks such as spell checking, grammar correction, and semantic understanding. The various noise types provide diverse data to help models learn to identify and correct specific types of errors.
