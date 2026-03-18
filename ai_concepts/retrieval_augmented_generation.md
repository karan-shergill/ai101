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