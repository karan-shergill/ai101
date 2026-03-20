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