# NLP Practice with NLTK and SpaCy (Stemming & Limmitization )


Welcome to the NLP Practice repository! This repository contains various NLP (Natural Language Processing) practices using Python libraries such as NLTK and SpaCy. The exercises include Stemming, Lemmatization, POS Tagging, and Named Entity Recognition (NER).

## Table of Contents
- [Overview](#overview)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
  - [Stemming with NLTK](#stemming-with-nltk)
  - [Lemmatization with SpaCy](#lemmatization-with-spacy)
  - [POS Tagging with SpaCy](#pos-tagging-with-spacy)
  - [Named Entity Recognition with SpaCy](#named-entity-recognition-with-spacy)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository showcases hands-on practice with key NLP concepts using NLTK and SpaCy. It covers:
- Stemming: Reducing words to their root form using NLTK.
- Lemmatization: Converting words to their base form using SpaCy.
- POS Tagging: Assigning parts of speech to words using SpaCy.
- Named Entity Recognition (NER): Identifying and categorizing entities in text using SpaCy.

## Technologies Used
- Python 3.x
- NLTK
- SpaCy

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YourUsername/NLP-Practice.git
   cd NLP-Practice
   ```

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the required libraries:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download SpaCy's English model:**
   ```bash
   python -m spacy download en_core_web_sm
   ```

## Usage

### Stemming with NLTK

The script demonstrates how to perform stemming using NLTK's `PorterStemmer`. Stemming reduces words to their root forms, which may not always be actual words.

```python
from nltk.stem import PorterStemmer

stemmer = PorterStemmer()
words = ["eating", "eats", "eat", "ate", "adjustable", "rafting", "ability", "meeting"]

for word in words:
    print(word, "|", stemmer.stem(word))
```

### Lemmatization with SpaCy

Lemmatization converts words to their base or dictionary form. Unlike stemming, lemmatization provides real words as output.

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("eating eats eat ate adjustable rafting ability meeting better")

for token in doc:
    print(token, " | ", token.lemma_)
```

### POS Tagging with SpaCy

Part of Speech (POS) tagging assigns a grammatical category to each token in a text, such as noun, verb, adjective, etc.

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("Elon flew to mars yesterday. He carried biryani masala with him")

for token in doc:
    print(token," | ", token.pos_, " | ", spacy.explain(token.pos_))
```

### Named Entity Recognition with SpaCy

NER identifies and classifies named entities in text into categories such as person names, organizations, locations, monetary values, etc.

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("Tesla Inc is going to acquire Twitter Inc for $45 billion")

for ent in doc.ents:
    print(ent.text, " | ", ent.label_, " | ", spacy.explain(ent.label_))
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you'd like to contribute to this repository.

## License

This repository is licensed under the MIT License.

---

You can customize the repository name, clone link, and other sections according to your preferences.
