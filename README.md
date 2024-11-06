# NLP-Text-Preprocessing

## How did I learn text preprocessing?
I learned text preprocessing from the article 'SPACY for Beginners - NLP' on the Medium platform, created by Pema Grg. It was easy to understand, and I referred to it to improve my skills.

[SPACY for Beginners -NLP](https://blog.ekbana.com/nlp-for-beninners-using-spacy-6161cf48a229)

#### Importing SpaCy
```python
import spacy
nlp = spacy.load("en_core_web_sm")
```
#### Word Tokenization
Tokenization breaks sentences into individual words (tokens).

```python
import spacy
nlp = spacy.load("en_core_web_sm")

text = """Artificial Intelligence is transforming the world of technology. It is being used in various fields like healthcare, finance, and education."""
doc = nlp(text)
words = [token.text for token in doc]
print(words)
```
#### Sentence Tokenization
To break text into a list of sentences

```python
import spacy
nlp = spacy.load("en_core_web_sm")

text = """Deep Learning is a subset of Machine Learning. It utilizes neural networks to analyze various forms of data."""
doc = nlp(text)
sentences = list(doc.sents)
print(sentences)
```
#### Stop Words Removal
We can remove irrelevant words (stop words) that do not contribute much information

```python
import spacy
from collections import Counter

nlp = spacy.load("en_core_web_sm")
text = """The quick brown fox jumps over the lazy dog. It is a classic pangram in English."""
doc = nlp(text)

# Remove stopwords and punctuations
filtered_words = [token.text for token in doc if not token.is_stop and not token.is_punct]
print(filtered_words)
```

#### Lemmatization
Lemmatization reduces words to their base or root form

```python
import spacy
nlp = spacy.load('en_core_web_sm')

text = """The children are playing in the park. They enjoyed their day."""
doc = nlp(text)

for token in doc:
    print(token.text, token.lemma_)
```
#### Getting Word Frequency
Counting the occurrence of words can help identify their significance in the text

```python
import spacy
from collections import Counter

nlp = spacy.load("en_core_web_sm")
text = """Data science is an interdisciplinary field that uses scientific methods, processes, algorithms, and systems to extract knowledge from data."""
doc = nlp(text)

# Remove stopwords and punctuations
words = [token.text for token in doc if not token.is_stop and not token.is_punct]
word_freq = Counter(words)
common_words = word_freq.most_common(5)
print(common_words)
```
#### Part-of-Speech (POS) Tagging
POS tagging helps identify the grammatical role of each word
```python
import spacy
nlp = spacy.load("en_core_web_sm")

text = """The weather today is wonderful and the sun is shining bright."""
doc = nlp(text)

for token in doc:
    print(token.text, token.pos_)
```

#### Named Entity Recognition (NER)
NER identifies named entities within the text

```python
import spacy
nlp = spacy.load("en_core_web_sm")

text = """Elon Musk is the CEO of SpaceX and Tesla, Inc. He was born in South Africa."""
doc = nlp(text)

labels = set([ent.label_ for ent in doc.ents]) 
for label in labels: 
    entities = [ent.text for ent in doc.ents if label == ent.label_] 
    entities = list(set(entities)) 
    print(label, entities)
```

### Project

After learning it, I worked on a project titled 'Extracting Information from Documents,' referring to YouTube. The channel name is 'NLP and CSS 201: Beyond the Basics.'
[youtube link](https://youtu.be/sUtthdcPyhc?si=niYdCKxDWglAZ9PL)
