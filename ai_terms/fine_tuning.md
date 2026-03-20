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