## Reasoning Models

### The Simple Definition
Reasoning Models are a special class of AI models that have been **trained to think deeply before answering** — spending time internally exploring a problem, checking their work, and reconsidering before giving a final response.

> Regular models **respond**. Reasoning models **think, then respond**.

### Real-Life Analogy

Think of the difference between two types of people answering a hard question:

**Regular model — the quick responder:**
> Someone fires an answer immediately based on instinct and memory. Fast. Usually fine for easy questions. But on hard problems — prone to mistakes.

**Reasoning model — the careful thinker:**
> Someone says *"give me a moment"*, picks up a pen, works through the problem on paper, crosses things out, tries a different approach, double checks — then gives a confident, well-reasoned answer.

Same person, same knowledge — but the **thinking process** makes the second answer far more reliable on hard problems.

### How is this different from Chain of Thought?

Great question — they're closely related but importantly different:

| | Chain of Thought | Reasoning Models |
|--|-----------------|-----------------|
| **What it is** | A prompting technique | A type of model |
| **Who controls it** | You — by adding instructions | Built into the model itself |
| **Thinking visible?** | Yes — in the response | Often hidden — internal only |
| **Training** | No special training needed | Specifically trained via RL to reason |
| **Quality** | Good | Much better — deeper, more reliable |

> CoT is like **asking** someone to show their work. Reasoning models are **trained from birth** to always think deeply — they can't help it.

### The Secret Ingredient — Reinforcement Learning

Remember Reinforcement Learning from last term? This is where it gets exciting.

Reasoning models are trained using RL with a very clever reward signal:
- **Getting the right answer** → reward ⬆️
- **Getting the wrong answer** → penalty ⬇️
- The model discovers **entirely on its own** that thinking step by step leads to more rewards

Nobody programmed the reasoning strategy in. The model **discovered through RL** that careful thinking leads to better outcomes — and kept doing more of it.

![reasoning_models.png](images/reasoning_models.png)

### Famous Reasoning Models Today

| Model | Company | Notable for |
|-------|---------|------------|
| **o1, o3** | OpenAI | First widely known reasoning models |
| **Claude 3.7 Sonnet** | Anthropic | Extended thinking mode — you can watch it reason |
| **Gemini 2.0 Flash Thinking** | Google | Fast reasoning at lower cost |
| **DeepSeek R1** | DeepSeek | Open source reasoning model — shocked the industry |

### The "Aha Moment" — Emergent Reasoning

One of the most fascinating discoveries about reasoning models is that when trained with RL, they developed behaviours **nobody programmed**:

- **Self-verification** — double checking their own answers
- **Backtracking** — saying *"wait, that's wrong, let me reconsider"*
- **Alternative approaches** — *"let me try a different method"*
- **Uncertainty acknowledgement** — *"I'm not sure about this step"*

These behaviours **emerged spontaneously** from RL training — the model discovered that these habits lead to more rewards. This is one of the most remarkable things happening in AI research right now.

### Thinking Tokens — The Cost of Reasoning

Reasoning models use special **thinking tokens** — tokens the model generates internally as it thinks, before producing the visible response.

- These thinking tokens **aren't shown to you** (usually)
- But they **cost compute time and money**
- A complex maths problem might use thousands of thinking tokens before giving a one-line answer

This is the core trade-off: **slower and more expensive, but dramatically more accurate** on hard problems.

### When to Use a Reasoning Model vs a Standard Model

| Task | Use |
|------|-----|
| Write me a poem | Standard model — faster, cheaper |
| Summarise this article | Standard model |
| Solve this calculus problem | Reasoning model |
| Debug this complex algorithm | Reasoning model |
| Plan my week | Either works |
| Prove this mathematical theorem | Reasoning model — definitely! |

### How Everything Connects

| Concept | Connection to Reasoning Models |
|---------|-------------------------------|
| **Chain of Thought** | The prompting technique that inspired reasoning models |
| **Reinforcement Learning** | How reasoning models are trained to think deeply |
| **Tokens** | Thinking tokens are the currency of reasoning |
| **Attention** | Attends over its own reasoning steps to stay on track |
| **Agents** | Reasoning models make far better agents — better planners |

### One Line Summary
> Reasoning models are AI models specifically trained — using Reinforcement Learning — to think through problems deeply before answering, exploring multiple paths, catching their own mistakes, and backtracking when needed.