## Quantisation

### The Simple Definition
Quantisation is a technique that **reduces the precision of the numbers** used to store a model's weights — making the model **smaller and faster** with surprisingly little loss in quality.

> It's like converting a high-resolution photo into a compressed JPEG — smaller file, still looks great, barely noticeable difference.

### Real-Life Analogy

Imagine measuring the temperature outside:

**High precision (32-bit):**
> "It is **23.48291746°C**"

**Quantised (4-bit):**
> "It is **23°C**"

For most purposes — deciding what to wear, planning a picnic — **23°C is perfectly good enough**. The extra decimal places are unnecessary precision that just wastes space.

Quantisation applies this same logic to the billions of numbers inside a neural network — **rounding them to use less storage** while keeping the model's behaviour almost identical.

### Why Does Precision Matter So Much?

Every number in a neural network (every weight) is stored in computer memory. The more precise the number, the more memory it takes:

| Format | Bits per number | Memory for 7B model |
|--------|----------------|---------------------|
| **FP32** (full precision) | 32 bits | ~28 GB |
| **FP16** (half precision) | 16 bits | ~14 GB |
| **INT8** (8-bit int) | 8 bits | ~7 GB |
| **INT4** (4-bit int) | 4 bits | ~3.5 GB |

> A 7 billion parameter model goes from needing a **$10,000 GPU** to fitting in **your laptop's RAM** — just by quantising!

![quantisation.png](images/quantisation.png)

### The Brilliant Bucket Trick

Here's the core idea made simple:

Imagine all the weights in a model range from **-3.0 to +3.0**.

**FP32** stores each number with full decimal precision — like a ruler marked in millimetres.

**INT4** divides that same range into just **16 buckets** (because 4 bits = 16 possible values):

```
Bucket:   0    1    2  ...  8  ...  14   15
Value:  -3.0 -2.6 -2.2 ... 0.0 ... 2.2  3.0
```

Every original weight gets **rounded to its nearest bucket**. The model stores the bucket number (0–15) instead of the precise decimal.

The rounding introduces a tiny error — but across billions of weights, these errors mostly **cancel each other out**, leaving model quality surprisingly intact.

### Types of Quantisation

| Type | How it works | Best for |
|------|-------------|---------|
| **Post-training quantisation (PTQ)** | Quantise after training is done | Fast, easy, most common |
| **Quantisation-aware training (QAT)** | Train the model while simulating quantisation | Best quality, but slower to train |
| **Mixed precision** | Different layers use different precision | Balance quality and speed per layer |
| **GGUF / GPTQ / AWQ** | Popular formats for quantised models | Running models locally with tools like Ollama |

### The Practical Magic — Running AI on Your Laptop

Thanks to quantisation, you can today:

- Download **Llama 3 (8B)** quantised to 4-bit — **~4.5 GB** — and run it entirely on your laptop
- Use **Ollama** or **LM Studio** — free tools that handle quantisation automatically
- Get responses in seconds with **no internet, no API key, no cost**

This was completely impossible just 3 years ago.

### Quantisation vs Distillation vs Pruning — the SLM trio

You've now learned all three model compression techniques:

| Technique | What it reduces | How |
|-----------|----------------|-----|
| **Distillation** | Model architecture size | Train small model to mimic large one |
| **Pruning** | Number of weights | Remove unimportant connections |
| **Quantisation** | Precision of weights | Round numbers to fewer bits |

They're often used **together** — distil first, then prune, then quantise — stacking the savings for maximum compression!

### How Everything Connects

| Concept | Connection to Quantisation |
|---------|--------------------------|
| **Vectorisation** | Vectors are stored as floating point numbers — quantisation compresses those |
| **SLM** | Quantisation is one of the key techniques to create SLMs |
| **Distillation** | Often applied together — distil then quantise |
| **Agents** | Quantised models enable agents to run on edge devices |
| **Fine-tuning** | Can fine-tune after quantisation to recover lost quality |

### One Line Summary
> Quantisation reduces the precision of a model's numbers from 32-bit decimals down to 4 or 8-bit integers — shrinking model size by up to 8x and enabling powerful AI to run on everyday devices like laptops and phones.