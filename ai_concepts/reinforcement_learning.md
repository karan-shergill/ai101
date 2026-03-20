## Reinforcement Learning (RL)

### The Simple Definition
Reinforcement Learning is a way of training AI where it **learns by trial and error** — taking actions, receiving rewards or penalties, and gradually figuring out the best strategy to maximise its reward.

> The AI is not told the right answer. It **discovers** the right answer by trying things and seeing what works.

### Real-Life Analogy

Think of **training a dog**:

- Dog sits when told → **treat** (reward)
- Dog jumps on guests → **"No!"** (penalty)
- Over many repetitions the dog learns: *sitting = good, jumping = bad*

Nobody gave the dog a manual. It learned purely from **feedback on its actions**.

Reinforcement Learning works exactly the same way — except instead of treats, the AI gets **numerical reward scores**.

### Another Analogy — Video Games

Imagine an AI learning to play a video game:

- It starts knowing **nothing** — pressing random buttons
- Sometimes it scores points (reward ⬆️)
- Sometimes it dies (penalty ⬇️)
- Over millions of games it figures out **exactly which button sequences score the most points**

No human told it the strategy. It **discovered the optimal strategy** purely through playing and learning from outcomes.

### The Three Core Elements

| Element | What it means | Dog analogy |
|---------|--------------|-------------|
| **Agent** | The AI doing the learning | The dog |
| **Environment** | The world it acts in | Your home |
| **Reward signal** | Feedback — good or bad | Treat or "No!" |

![reinforcement_learning.png](images/reinforcement_learning.png)

### RL vs The Other Learning Types

You've now learned three types of machine learning — here's how they compare:

| Type | How it learns | Example |
|------|--------------|---------|
| **Self-supervised** | Predicts hidden parts of data | Fill-in-the-blank on internet text |
| **Supervised** | Learns from labelled examples | "This email = spam" |
| **Reinforcement** | Learns from rewards and penalties | Trial and error with feedback |

Most modern LLMs like Claude use **all three** at different stages:
1. **Self-supervised** — pre-training on massive text
2. **Supervised** — fine-tuning on curated examples
3. **Reinforcement (RLHF)** — polishing behaviour with human feedback

### Famous RL Breakthroughs

RL has produced some of the most jaw-dropping AI achievements:

- **AlphaGo (2016)** — DeepMind's RL agent beat the world champion at Go — a game with more possible positions than atoms in the universe
- **OpenAI Five (2019)** — Beat world champion Dota 2 players after playing the equivalent of 45,000 years of games against itself
- **AlphaFold (2020)** — Used RL-inspired techniques to solve protein folding — a 50-year-old biology problem
- **Claude & ChatGPT** — RLHF makes responses helpful, safe, and aligned with human values

### The Explore vs Exploit Dilemma

One of the most fascinating challenges in RL:

**Exploit** — Keep doing what already works (safe but limited)
**Explore** — Try new things that might work better (risky but potentially much better)

Too much exploitation → the AI gets stuck doing the same thing forever
Too much exploration → the AI wastes time on random bad actions

Great RL systems **balance both** — like a chef who mostly makes their best dishes but occasionally experiments with new recipes.

### One Line Summary
> Reinforcement Learning is a training method where AI learns by trying actions, receiving rewards or penalties, and gradually discovering the best strategy — like training a dog, but with numbers instead of treats.