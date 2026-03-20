## Multi-modal Models

### The Simple Definition
A Multi-modal Model is an AI that can **understand and work with multiple types of input** — not just text, but also images, audio, video, documents, and more — all within the same model.

> "Modal" means type of data. "Multi-modal" means **many types of data**.

### Real-Life Analogy

Think about how **you** experience the world:

You don't just read text. You **see** images, **hear** sounds, **watch** videos, **read** documents — and your brain combines all of these seamlessly into one understanding.

When a friend sends you a photo of a restaurant menu and asks *"what should I order?"* — you read the text on the menu, look at the food photos, and combine it all to give advice.

**Multi-modal models do exactly this** — they process different types of information and reason across all of them together.

### The Evolution of AI Modalities

| Era | What AI could handle |
|-----|---------------------|
| **Early AI** | Text only |
| **Image AI** | Images only (separate models) |
| **Multi-modal AI** | Text + images together |
| **Today's frontier** | Text + images + audio + video + documents + code |

![multi_modal_models.png](images/multi_modal_models.png)

### The Secret — A Shared Vector Space

Remember **Vectorisation** from early in our journey? This is where it pays off beautifully.

The trick behind multi-modal models is converting **every type of input into the same kind of vector**:

- An image of a cat → vector `[0.9, 0.1, 0.8...]`
- The word "cat" → vector `[0.9, 0.1, 0.7...]`

**They end up close together in vector space!** This means the model understands that the image and the word refer to the same concept — purely through numbers. This is called a **shared embedding space**.

### Real World Examples

**Claude**
> Upload a photo of your handwritten notes → Claude reads and summarises them
> Share a screenshot of an error → Claude diagnoses the bug

**GPT-4o by OpenAI**
> Speak to it naturally → it understands your voice, tone, and emotion
> Show it a maths problem on paper → it solves it

**Gemini by Google**
> Show it a video → it describes what's happening frame by frame
> Share a chart → it analyses the data trends

### Input vs Output Modalities

Not all multi-modal models can both **receive and produce** every type:

| Model type | Input | Output |
|-----------|-------|--------|
| **Vision-language** | Text + images | Text only |
| **Speech models** | Text + audio | Text + audio |
| **Full multi-modal** | Text + image + audio + video | Text + image + audio |
| **Omni models** | Everything | Everything |

### Why This is Hard to Build

Combining modalities is technically very challenging:

- **Different data structures** — text is sequential, images are grids of pixels, audio is waves
- **Different scales** — an image has millions of pixels, a sentence has tens of words
- **Alignment problem** — teaching the model that a photo of a dog and the word "dog" mean the same thing

The breakthrough that made this possible was — you guessed it — **the Transformer and the shared vector space**. Attention can operate across any sequence of vectors, regardless of what they originally came from.

### How Everything Connects

| Concept | Connection to Multi-modal Models |
|---------|--------------------------------|
| **Vectorisation** | Every modality gets converted to vectors |
| **Attention** | Attends across all modalities simultaneously |
| **Transformer** | Architecture flexible enough to handle any input |
| **Fine-tuning** | Models fine-tuned on paired data (image + caption) |
| **RAG** | Can now retrieve images AND text as context |

### One Line Summary
> Multi-modal models are AI systems that can understand and reason across multiple types of input — text, images, audio, video, and more — all within a single unified model, just like a human brain.