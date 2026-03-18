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