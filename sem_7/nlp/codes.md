# Codes

## MS Word `.docx`

```py
from docx import Document
doc = Document("mydoc.docx")

for p in range doc.paragrapghs:
  print(p)
```

## text extract from PDF

```py
from pypdf import PdfReader
pdf = PdfReader("mypdf.pdf")

for p in range pdf.pages:
  print(p.extract_text())
```

## BeutifulSoup to remove HTML

```py
from bs4 import BeutifulSoup
html = "some html code"

bs = BeutifulSoup(html, "html.parser")
text = bs.get_text()
```

## Normalize text using lowercase, tokenization, stemming, and lemmetization

```py
text = "some text"

import nltk
from nltk.tokenize import word_tokenize
from nltk.stem import PorterStemmer
from nltk.stem import WordNetLemmetizer

text = text.lower()
tokens = text.word_tokenize()

# stemming
stemmer = PorterStemmer()
stems = [stemmer.stem(word) for word in tokens]

# lemmetization
lemmetizer = WordNetLemmetizer()
lemms = [lemmetizer.lemmetize(word) for word in tokens]
```

## Usual words

```py
from nltk.corpus import gutenberg, words

def unusual_words(text):
    text_vocab = set(w.lower() for w in text if w.isalpha())
    english_vocab = set(w.lower() for w in words.words())
    unusual = text_vocab - english_vocab
    return sorted(unusual)

text = gutenberg.words("austen-sense.txt")

print(unusual_words(text))
```

## String operations

### Concatenation

```py
a = "Natural"
b = "Language"

print(a + " " + b)
```

### Multiplication

```py
print("NLP " * 3)
# output: NLP NLP NLP
```

### `join()`

```py
words = ["hello", "word"]
print(" ".join(words))
```

### `split()`

```py
text = "Hello World"
words = text.split()
# output: ["Hello", "World"]
```

## Conditional Statements

```py
word = "hello"

if word.islower():
    print("The word is lowercase")
else:
    print("The word is not lowercase")

##################

marks = 75

if marks >= 75:
    print("Distinction")
elif marks >= 50:
    print("Pass")
else:
    print("Fail")
```

## NLTK expressions to-

### (a) extract last two words of text2

```py
import nltk
from nltk.book import text2

print(text2[-2:])
```

### (b) Find all words in text6 containing z

```py
from nltk.book import *

for w in text6:
  if 'z' in w:
    print(w)
```

## `islower()`, `istitle()` to classify tokens

```py
from nltk.book import sent1

for word in sent1:
    if word.islower():
        print(word, "-> lowercase")
    elif word.istitle():
        print(word, "-> titlecase")
    else:
        print(word, "-> punctuation/other")
```

## words in `text1` longer than 4 characters and frequency > 100

```py
from nltk.book import *

[w for w in set(text1) if len(w) > 4 and text1.count(w) > 100]
```
