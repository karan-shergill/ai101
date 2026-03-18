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