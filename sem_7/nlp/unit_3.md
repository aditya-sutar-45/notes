# Unit 3

## NLP Pipeline

- sequence of stages through which natural language is processed
- convert raw text → structured information

### Stages of NLP

1. Text / Speech Input
2. Preprocessing
3. Language Analysis
4. Text Representation and embeddings
5. Model Training
6. Output Generation

## Applications of Regular Expressions

- Text Searching and Pattern Matching

```md
pattern: cat
text: "the cat is sitting on mat."
output: cat
```

- Tokenization
  - divide text input numbers, words or other tokens

```md
text: "NLP is easy"
pattern: \w+
output: NLP, is, easy
```

- Finding Numbers

```md
pattern: \d+
\d → digit, + → one more more occurances
text: "i have 25 books"
output: 25
```

- Finding email Addresses

```md
pattern: [\w.-]+@[\w.-]+\.\w+
```

- Finding URL's

```md
pattern: https?:://\S+
```

- text cleaning and replacement
- extract specific information

## Spoken Dialog System

- allows users to interact with a computer using spoken language
- listens to user's speech, understands the meaning
- decined appropriate response, generates a reply

```md
user → speech recognizer → NLU → dialoge manager
→ NL generation → TTS → user(spoken reply)
```
