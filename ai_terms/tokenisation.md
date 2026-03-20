## Tokenisation

### The Simple Definition
Before an LLM can understand your text, it needs to **break it into small chunks** called **tokens**. This process of breaking text into chunks is called **tokenisation**.

> An LLM doesn't read words like we do — it reads **tokens**.

### Real-Life Analogy

Think of it like a **pizza being sliced**.

The whole pizza = your sentence.
Each slice = a token.

You don't eat the whole pizza at once — you eat it **slice by slice**. Similarly, the LLM doesn't read your sentence all at once — it processes it **token by token**.

### What exactly is a token?

A token can be:
- A **whole word** → `cat` = 1 token
- A **part of a word** → `unbelievable` = `un` + `believ` + `able` = 3 tokens
- A **punctuation mark** → `.` or `!` = 1 token
- A **space + word** → ` the` = 1 token

### Example — let's tokenise a sentence!

![tokenisation.png](images/tokenisation.png)

### Why does this matter?

**1. LLMs think in tokens, not words**
When you send a message, it gets converted to tokens first, then the LLM processes them one by one.

**2. Cost & limits are measured in tokens**
Most AI APIs charge you **per token**. A typical page of text ≈ 500–700 tokens.

**3. Longer words = more tokens**
Simple words like `cat` = 1 token. Complex words like `unbelievable` = 3 tokens. This is why AI can sometimes struggle more with rare or technical words.

### Quick Rule of Thumb
> 🧮 **~1 token ≈ ¾ of a word** in English
> So 100 words ≈ roughly 130–140 tokens

### One Line Summary
> Tokenisation is the process of chopping your text into small bite-sized pieces (tokens) that an LLM can actually understand and process.