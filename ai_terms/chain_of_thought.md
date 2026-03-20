## Chain of Thought (CoT)

### The Simple Definition
Chain of Thought is a prompting technique where you encourage the AI to **show its reasoning step by step** before giving a final answer — rather than jumping straight to a conclusion.

> Instead of asking the AI for an answer, you ask it to **think out loud** first.

### Real-Life Analogy

Think back to **maths class**:

**Bad student habit:**
> *Question: "If a train travels 60 mph for 2.5 hours, how far does it go?"*
> Student writes: **"150"** ← just the answer, no working shown

**Good student habit:**
> *"Speed = 60 mph. Time = 2.5 hours. Distance = Speed × Time. So Distance = 60 × 2.5 = 150 miles."*

The second student is **less likely to make mistakes** because each step checks the previous one. If something goes wrong, you can see exactly where.

Chain of Thought makes the AI work like the **good student** — showing every step of its reasoning.

### Why does showing steps help?

This seems almost too simple — but it works for a deep reason.

Remember how LLMs generate text? **Token by token**, each word influenced by everything before it. When the AI writes out its reasoning step by step, each new step is informed by the **correct previous steps** — building a chain of correct logic rather than guessing the end from the beginning.

> Writing the reasoning **is** the reasoning. The act of generating the steps actually helps the model think more accurately.

### The Two Ways to Use CoT

**1. Zero-shot CoT** — Just add a magic phrase:
> *"Let's think step by step."*
> That's literally it — and it measurably improves accuracy!

**2. Few-shot CoT** — Show examples of step-by-step reasoning:
> Give 2–3 examples where you show the full working, then ask your question.

![chain_of_thought.png](images/chain_of_thought.png)


### CoT and Extended Thinking

You may have heard about **extended thinking** in models like Claude. This is CoT taken to the next level:

- The model gets a **dedicated thinking space** before it responds
- It reasons through the problem extensively — exploring multiple paths, second-guessing itself, backtracking
- Only then does it produce its final polished answer

> It's like the difference between answering a question off the top of your head vs having 10 minutes to **think it through on a whiteboard** first.

This is one reason why newer AI models are dramatically better at hard reasoning tasks — they're not just answering, they're **genuinely thinking first**.

### The "Let's Think Step by Step" Experiment

Researchers at Google found that simply adding the phrase:

> *"Let's think step by step."*

...to a prompt increased AI accuracy on maths problems from **17.7% to 78.7%** — a massive jump from four words!

This is one of the most striking results in all of prompt engineering research.

### How CoT Connects to What You've Learned

| Concept | Connection to CoT |
|---------|------------------|
| **Attention** | Each reasoning step attends to previous steps — building correctly |
| **Tokens** | More tokens = more reasoning space = better answers |
| **Few-shot prompting** | CoT examples are a special type of few-shot prompt |
| **Agents** | Agents use CoT internally to plan their next action |
| **Context Engineering** | Including CoT instructions is a key context engineering technique |


### When CoT is NOT helpful

CoT isn't always the answer:

- **Simple factual questions** — *"What is the capital of France?"* — no need for steps
- **Creative writing** — reasoning steps can interrupt the creative flow
- **Time-sensitive tasks** — CoT uses more tokens and takes slightly longer

Use it when the task involves **multiple steps, logic, or calculation** — skip it for straightforward lookups.

### One Line Summary
> Chain of Thought is a technique where you ask the AI to reason through a problem step by step before answering — dramatically improving accuracy on complex tasks by making the AI think out loud.