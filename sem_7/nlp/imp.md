# IMP

## Regular expressions

- regex is a pattern used to search, match or replace specific text pattern
- useful for processing and cleaning textual data

### identifying specific word patterns

```py
import re
result = re.findall(r'cat|dog', text)
```

### identifying numbers

```py
import re
result = re.findall(r'[0-9]+', text)
```

### identifying dates

```py
# eg: 02/12/2023
result = re.findall(r'\d{2}/\d{2}/\d{4}', text)
# \d{2} → exactly 2 digits
# / match slash
```

### identifying email

```py
import re
result = re.findall(r'[\w.-]+@[\w.-]+\.\w+', text)
```

### identifying words ending with specific suffix

```py
import re
# words ending with "ing"
result = re.findall(r'\w+ing', text)
```

## String processing methods

- string → sequence of characters
- NLP, strings used for normalization, tokenization, searching, cleaning etc

### String methods

1. `lower()`
2. `upper()`
3. `strip()`
4. `split()` → splits string into list of words
5. `join()` → joins list elements into one string `" ".join(words)`
6. `replace()` → `test.replace("NLP", "AI")`
7. `find()` → `text.find("ugga")`
8. `startswith()` → `text.startswith("i")`
9. `endswith()`

#### example program

```py
text = "  hello world  "
text = text.strip()
lower_text = text.lower()
upper_text = text.upper()
new_text = text.replace("word", "aditya")
words = text.split()
joined_text = "-".join(words)
pos = text.find("world")
```

## important functions defined for FreqDist

- `FreqDist` → records how many times each unique word or item occurs

```py
from nltk import FreqDist
words = ['apple', 'banana', 'apple', 'orange',
         'apple', 'banana', 'mango']
fdist = FreqDist(words)
```

### important functions

1. `FreqDist(words)` → creates a freq distribution
2. `fdist[word]` → gives count of particular word
3. `fdist[word]+=1` → increments count of word
4. `fdist.freq(word)` → gives freq of a word
5. `fdist.N()` → gives total number of samples
6. `fdist.most_common(n)` → gives n most frequent samples
7. `fdist.max()` → sample having max count

## program identify words occuring atleast 3 times in brown corpus

```py
import nltk
from nltk.corpus import brown
from nltk.probabilty import FreqDist

nltk.download("brown")
words = brown.words()
fdist = FreqDist(words)

for w, f in fdist.items():
  if f >= 3:
    print(w, ":", f)
```

## Word comparison operators

- relational operators used in python to compare two words/strings
- useful in NLP for checking equality, ordering, applying conditions

### operators

1. `==` → equal to
2. `!=` → not equal
3. `<` → less than (checks **lexicographical** order)
4. `>` → greater than
5. `<=` → less than equal to
6. `>=` → greater than equal to
