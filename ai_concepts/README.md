# AI Terms

<details>
  <summary>LLM — Large Language Model</summary>

##  LLM — Large Language Model

### The Simple Definition
An LLM is an **AI that has read a massive amount of text** (books, websites, articles, code, etc.) and learned how to **understand and generate human language** from it.

### Real-Life Analogy

Imagine a student who has **read millions of books, articles, and websites** their entire life. Now when you ask them a question or give them a topic — they can **write about it, answer it, or have a conversation** because of everything they've absorbed.

An LLM is that student — except it's a computer program.

### Breaking Down the Name

| Word | What it means |
|------|--------------|
| **Large** | Trained on a huge amount of text data (think billions of web pages) |
| **Language** | It works with human language — reading and writing it |
| **Model** | A mathematical system that learned patterns from all that text |

### How does it actually work? (Super Simply)

You give it some text → It **predicts what comes next** — word by word.
That's literally it at the core!

![img.png](images/llm.png)

### Real Examples of LLMs
- **ChatGPT** by OpenAI
- **Claude** by Anthropic
- **Gemini** by Google

### One Line Summary
> An LLM is a very well-read AI that learned how to talk by reading most of the internet — and now predicts the best words to respond to you.

</details>

<details>
  <summary>Tokenisation</summary>

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

</details>

<details>
  <summary>Vectorisation</summary>

## Vectorisation (also called "Embeddings")

### The Simple Definition
After tokenisation, the LLM needs to convert each token into a **list of numbers** so the computer can do math on it. This process is called **vectorisation**.

> Computers don't understand words — they only understand numbers. Vectorisation is the **translation layer** between human language and machine math.


### Real-Life Analogy

Think of it like a **GPS coordinate system**.

- Every city in the world has a unique location: `(latitude, longitude)`
- London = `(51.5, -0.1)`, Tokyo = `(35.7, 139.7)`
- You can now **measure distance** between cities using math

Vectorisation does the same for words:
- Every word gets a unique "location" in **meaning space**
- `king` = `[0.2, 0.8, 0.5, ...]`, `queen` = `[0.2, 0.7, 0.9, ...]`
- Now you can measure how **similar or different** words are — using math!

### The Magic Part

Because words are now numbers, you can do **arithmetic on meaning**:

> king − man + woman ≈ queen

The model understands relationships between concepts purely through numbers!
![vectorisation.png](images/vectorisation.png)

### One Line Summary
> Vectorisation turns words into lists of numbers so that the computer can understand meaning mathematically — and words with similar meanings end up with similar numbers.

</details>

<details>
  <summary>Attention</summary>

## Attention (Self-Attention)

### The Simple Definition
Attention is how an LLM figures out **which words in a sentence are most important to each other** when trying to understand meaning.

> It's the LLM asking: *"When I'm reading this word, which other words should I pay attention to?"*


### Real-Life Analogy

Imagine reading this sentence:

> *"The animal didn't cross the street because **it** was too tired."*

What does **"it"** refer to? The animal? The street?

Your brain **automatically focuses** on "animal" because it makes more sense in context. You ignored "street" for this purpose.

That's exactly what attention does — it helps the LLM figure out **which words are connected to which**, even across long distances in a sentence.

### Another Analogy — The Spotlight 

Imagine a stage with many actors (words). When one actor speaks, a **spotlight** shines on the other actors that are most relevant to what they're saying. Brighter spotlight = more attention.

![attention.png](images/attention.png)

### The Q, K, V Trio — Simply Explained

Every word gets 3 roles simultaneously:

| Role | Question it asks | Analogy |
|------|-----------------|---------|
| **Q — Query** | "What am I looking for?" | A Google search query |
| **K — Key** | "What topic do I cover?" | A book's index keyword |
| **V — Value** | "What info do I actually carry?" | The book's actual content |

When word **"it"** (Query) searches for meaning, it matches against every other word's **Key**. The best match (animal) gets the highest score, so its **Value** (meaning) flows back strongly into "it".

### Why is Attention so powerful?

Before attention, AI read sentences **left to right, one word at a time** like a typewriter. It would often forget earlier words by the time it reached the end.

Attention lets the model **look at ALL words simultaneously** and decide what's relevant — no matter how far apart they are in the sentence.

### One Line Summary
> Attention is how the LLM figures out which words are connected to which — so it understands that "it" means "the animal", not "the street".

</details>

<details>
  <summary>Self-Supervised Learning</summary>

## Self-Supervised Learning

### The Simple Definition
Self-Supervised Learning is a way of training an AI where the **data creates its own labels automatically** — no human needed to manually tag anything.

> The AI learns by playing a **fill-in-the-blank game** with text — over and over, billions of times.

### Real-Life Analogy

Remember doing **fill-in-the-blank exercises** in school? 

> *"The sky is ____."* → You write "blue"

Nobody had to tell you the answer beforehand — you already knew from **experience reading and hearing** that sentence pattern your whole life.

Self-supervised learning works the same way:
- Take a sentence from the internet
- **Hide a word**
- Ask the AI to guess it
- Tell the AI if it was right or wrong
- **Repeat billions of times**

The AI gradually gets better and better — and in doing so, it learns grammar, facts, reasoning, and meaning — all on its own!

![self_supervised_learning.png](images/self_supervised_learning.png)

### What does the AI actually learn from this? 

By playing this guessing game **billions of times**, the AI doesn't just memorise answers — it picks up much deeper knowledge:

- **Grammar** — "The cat ___ on the mat" → needs a verb
- **Facts** — "The capital of France is ___" → Paris
- **Reasoning** — "If it's raining, take an ___" → umbrella
- **Style** — "Once upon a time ___" → story language follows

Nobody programmed any of this in. It all **emerged naturally** from the guessing game!

### The clever trick

The magic is that **every sentence on the internet is simultaneously**:
- The **training data** (input text)
- The **label** (the hidden word answer)

So the entire internet becomes a free, infinite training set!

### One Line Summary
> Self-supervised learning is how an LLM teaches itself by playing a fill-in-the-blank game on billions of internet sentences — no human labelling needed.

</details>

<details>
  <summary>Transformer</summary>

## Transformer

### The Simple Definition
A Transformer is the **overall architecture (design/structure)** of how modern LLMs are built. It's the blueprint that combines everything you've learned so far into one powerful system.

> If an LLM is a car , the Transformer is the **engine design** that makes it work.


### Real-Life Analogy

Think of a **busy post office** that processes thousands of letters simultaneously:

- Each letter (token) gets **read by everyone at once** — not one by one
- Sorters (attention heads) figure out **which letters relate to which**
- The whole batch gets processed **in parallel**, not sequentially

Before Transformers, AI read text like a slow typist — **one word at a time, left to right**. The Transformer said: *"Why not read everything at once?"* That single idea changed everything.


### The origin — "Attention is All You Need" 

In 2017, Google researchers published a paper with that exact title. It introduced the Transformer. Within a few years, it became the foundation of **GPT, Claude, Gemini, BERT** — essentially every major AI system today.

![transformer.png](images/transformer.png)

### What's inside each Transformer layer?

Each layer has **two key parts** working together:

**1. Self-Attention** (you already know this!)
Figures out which words relate to which — "it" → "animal"

**2. Feed-Forward Network**
A mini neural network that takes the attention output and **transforms it further** — adding deeper reasoning and pattern recognition on top.

Then each layer passes its output **up to the next layer**, each one building a richer and richer understanding of the text.

### Why stacking layers matters

| Layer | What it tends to learn |
|-------|----------------------|
| Early layers | Grammar, spelling, word structure |
| Middle layers | Facts, relationships, context |
| Deep layers | Complex reasoning, tone, logic |

GPT-3 has **96 layers**. Claude and GPT-4 likely have even more. Each layer refines the understanding further.

### The secret superpower

The Transformer processes **all tokens simultaneously** — not one by one. This means:
- It can be trained on **massive data very fast** (using GPUs in parallel)
- It can **attend to any word** no matter how far away in a sentence
- It **scales beautifully** — more layers + more data = smarter AI

### One Line Summary
> A Transformer is the architectural blueprint of modern AI — it stacks multiple layers of attention and reasoning on top of each other to understand and generate language with remarkable depth.

</details>

<details>
  <summary>Fine-tuning</summary>

## Fine-Tuning

### The Simple Definition
Fine-tuning is the process of taking an already-trained LLM and **training it further on a smaller, specific dataset** to make it better at a particular task or behaviour.

> Think of it as **taking a university graduate and giving them specialised job training**.


### Real-Life Analogy

Imagine a **medical student** :

- They spend **6 years in medical school** learning everything — biology, chemistry, physics, anatomy (this is **pre-training**, like the Transformer stage)
- Then they do a **2-year residency** specialising in cardiology — focused, specific, real-world training (this is **fine-tuning**)

The residency doesn't erase everything they learned. It **builds on top of it** and sharpens their skills for a specific job.

An LLM works exactly the same way!


### Pre-training vs Fine-tuning at a glance

| | Pre-training | Fine-tuning |
|--|-------------|-------------|
| **Data** | Trillions of internet words | Thousands of curated examples |
| **Time** | Weeks to months | Hours to days |
| **Cost** | Millions of dollars | Much cheaper |
| **Goal** | Learn language & world knowledge | Learn specific behaviour or task |
| **Who does it** | AI labs (Anthropic, OpenAI) | Companies, developers, researchers |

![fine_tuning.png](images/fine_tuning.png)


### A special type of fine-tuning — RLHF

One of the most important fine-tuning techniques is called **RLHF — Reinforcement Learning from Human Feedback**. This is how Claude and ChatGPT were made to be **helpful, harmless, and honest**.

Here's how it works simply:

1. The base LLM generates several responses to a question
2. **Human raters** rank which response is best
3. The model learns from those rankings
4. It gradually gets better at giving responses humans prefer

> This is why Claude doesn't just dump raw information — it explains things clearly, stays safe, and avoids harmful content. That behaviour was **fine-tuned in** via RLHF!

### What fine-tuning does NOT do 

Fine-tuning **doesn't add new knowledge** — it shapes **behaviour and style**. For example:
- It can make the model respond only in formal English ✅
- It can make the model always answer as a customer service agent ✅
- It **cannot** teach the model facts about events after its training cutoff ❌


### One Line Summary
> Fine-tuning takes a general-purpose LLM and gives it specialised training on a focused dataset — turning a generalist into an expert for a specific task or behaviour.


</details>

<details>
  <summary>Few-shot Prompting</summary>

## Few-Shot Prompting

### The Simple Definition
Few-shot prompting is a technique where you **give the AI a few examples** of what you want **inside your prompt itself**, before asking it to do the actual task.

> You're not training the AI — you're just **showing it the pattern** you want it to follow, right in the conversation.

### Real-Life Analogy

Imagine you're a **new employee** and your boss gives you a task:

**Bad briefing:**
> "Write product descriptions for our store."

You'd probably guess what format they want and get it wrong.

**Good briefing:**
> "Here are two product descriptions we've already written... *(shows examples)*... Now write one for this new product."

Now you know exactly the **tone, length, and format** they want. That's few-shot prompting!

### The "Shot" Family

| Name | Examples given | When to use |
|------|---------------|-------------|
| **Zero-shot** | 0 examples | Simple tasks AI already knows well |
| **One-shot** | 1 example | When you have one clear example |
| **Few-shot** | 2–5 examples | Best for specific patterns or formats |
| **Many-shot** | 10+ examples | Complex, highly specific tasks |

![few_shot_prompting.png](images/few_shot_prompting.png)

### Real Examples You Can Use Today 

**Example 1 — Tone matching:**
> Write product titles in this style:
> "Noise-cancelling headphones" → "Silence the World, Hear Your Music"
> "Waterproof jacket" → "Stay Dry, Look Sharp"
> Now do: "Running shoes" → ?

**Example 2 — Data formatting:**
> Convert to structured format:
> "John, 28, New York" → Name: John | Age: 28 | City: New York
> "Sara, 34, London" → Name: Sara | Age: 34 | City: London
> Now do: "Ahmed, 22, Dubai" → ?

### Why does it work?

Remember **Attention** and **Vectorisation**? The AI uses those mechanisms to detect the **pattern** in your examples and continue it. You're essentially guiding the attention mechanism by showing it exactly what relationships matter to you.

You're not changing the model — you're giving it a **very strong hint** from inside the prompt itself.

### Few-shot vs Fine-tuning — what's the difference?

| | Few-shot prompting | Fine-tuning |
|--|-------------------|-------------|
| **Where** | Inside the prompt | Changes the model weights |
| **Cost** | Free, instant | Expensive, takes time |
| **Persistence** | Only for that conversation | Permanent change |
| **Best for** | Quick formatting, style | Deep behavioural change |


### One Line Summary
> Few-shot prompting means giving the AI 2–5 examples of what you want inside your prompt, so it learns your exact pattern and follows it — no training required.

</details>

<details>
  <summary>Retrieval Augmented Generation</summary>

## RAG — Retrieval Augmented Generation

### The Simple Definition
RAG is a technique where instead of relying only on what the LLM learned during training, it first **fetches relevant information from an external source** and then uses that to generate its answer.

> The LLM gets to **look things up** before answering — like an open-book exam instead of a closed-book one.

### The Problem RAG Solves

LLMs have two big limitations:

**1. Knowledge cutoff** — They only know things up to when they were trained. Ask Claude about news from last week? It won't know.

**2. Hallucination** — When an LLM doesn't know something, it sometimes **makes up a confident-sounding answer**. This is dangerous in fields like medicine, law, and finance.

RAG fixes both problems by giving the LLM **real, fresh, verified information** to work from.

### Real-Life Analogy

Imagine two types of doctors️:

**Doctor A (no RAG):** Answers purely from memory of medical school. Confident, but might be outdated or occasionally wrong.

**Doctor B (with RAG):** Before answering, quickly pulls up your medical records, latest research papers, and current treatment guidelines — then gives you an answer based on all of that.

Doctor B is going to give you a much better answer! That's RAG.

![retrieval_augmented_generation.png](images/retrieval_augmented_generation.png)

### RAG vs Pure LLM — head to head

| | Pure LLM | LLM with RAG |
|--|---------|-------------|
| **Knowledge** | Only what it was trained on | Any external document you give it |
| **Up to date?** | No — has a cutoff date | Yes — can use live data |
| **Hallucination risk** | Higher | Much lower |
| **Can cite sources?** | No | Yes! |
| **Cost** | Cheaper | Slightly more compute |
| **Best for** | General conversation | Specific, factual, domain tasks |

### Real World RAG Examples 

- **Customer support bot** — searches your company's FAQ and policy documents before answering
- **Legal AI** — retrieves relevant case law before giving advice
- **Medical assistant** — pulls latest research papers before suggesting treatments
- **This conversation!** — When I use web search to find current information, that's RAG in action 

### The clever bit — Vector Search

Remember **Vectorisation** from earlier? RAG uses it brilliantly:

1. All your documents are pre-converted to vectors and stored in a **vector database**
2. Your question is also converted to a vector
3. The system finds documents whose vectors are **closest** (most similar) to your question vector
4. Those documents get retrieved — fast, even across millions of pages!

### One Line Summary
> RAG lets an LLM look up relevant information from external documents before answering — making it more accurate, up-to-date, and trustworthy than relying on memory alone.

</details>


<details>
  <summary>Vector Database</summary>

## Vector Database

### The Simple Definition
A Vector Database is a special type of database designed to **store, search, and retrieve vectors** (those lists of numbers from Vectorisation) extremely fast — by finding the ones that are **most similar** to a given query vector.

> It's a database that understands **meaning**, not just exact matches.

### Real-Life Analogy

Think of a **regular library vs a smart librarian**:

**Regular database** (like a filing cabinet):
> "Find me the file named exactly *cat.txt*"
> If you search for "feline", you get nothing. It only matches exact names.

**Vector database** (the smart librarian):
> "Find me everything related to cats"
> Returns: files about cats, kittens, felines, pets, lions — because it understands **similarity of meaning**!

That's the superpower of a vector database — it finds things by **how similar their meaning is**, not by exact word matching.

### Regular Database vs Vector Database

| | Regular Database | Vector Database |
|--|----------------|----------------|
| **Stores** | Text, numbers, dates | Vectors (lists of numbers) |
| **Searches by** | Exact match | Similarity of meaning |
| **Query example** | `WHERE name = 'cat'` | "Find me things like cat" |
| **Good for** | Structured records | Semantic / meaning search |
| **Examples** | MySQL, PostgreSQL | Pinecone, Weaviate, ChromaDB |

![vector_database.png](images/vector_database.png)

### How similarity is measured — Cosine Similarity

The most common way vector databases measure similarity is called **cosine similarity**. Simply put:

- Two vectors pointing in the **same direction** = very similar (score close to 1.0)
- Two vectors pointing in **opposite directions** = very different (score close to 0.0)

Think of it like two arrows on a compass — the closer their directions, the more similar their meaning!

### How it all connects — RAG + Vector DB together

You now know the complete RAG pipeline with Vector DB:

1. **Documents** get converted to vectors → stored in **Vector Database**
2. User asks a question → question converted to a vector
3. **Vector Database** finds the most similar document vectors
4. Those documents are retrieved and sent to the **LLM**
5. LLM generates a grounded, accurate answer

> The Vector Database is the **fast, smart search engine** inside RAG!


### Popular Vector Databases 

| Tool | Best known for |
|------|---------------|
| **Pinecone** | Managed, easy to use, production ready |
| **Weaviate** | Open source, flexible |
| **ChromaDB** | Lightweight, great for local development |
| **Qdrant** | Fast, open source, Rust-based |
| **pgvector** | Adds vector search to regular PostgreSQL |

### One Line Summary
> A Vector Database stores text as vectors (numbers) and retrieves the most meaningfully similar ones to a query — making it the backbone of semantic search and RAG systems.

</details>