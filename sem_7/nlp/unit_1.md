# Unit 1

## Spoken Dialog System

- tech that allos humans to interact with computers using speech
- voice assistants

### Stages

1. Phonology
2. Morphology
3. Syntax
4. Sementics
5. Reasoning

## Counting Vocabulary

1. `set()` → unique elements `set(text)`
2. `sorted()` →arranges words in alpha order `sorted(set)`
3. `len()` → lenght

## Lexical Dispersion Plot

- graphical representation
- shows where words occur throuout text

```md
| Word Beginning End |
| ------------------ |
| freedom            |     |     |     |     |     |
| democracy          |     |     |     |     |
| people             |     |     |     |     |     |     |     |     |     |
| government         |     |     |     |     |
```

1. rows → each word
2. vertical stripes → occurance of that word
3. timeline → start to end of text

```py
from nltk.book import *
text4.dispersion_plot(["freedom", "democracy", "people"])
```

## Collocations and Bigrams

### Bigrams

- sequence of two consecutive words occuring together

```py
from nltk import bigrams

words = ["natural", "language", "processing", "is", "useful"]
list(bigrams(words))
```
