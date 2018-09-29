# Evaluation of sentence embeddings in downstream and linguistic probing tasksTLDR

### What contribution？

Mainly contribution is, giving an extensive evaluation for different kind of word embedding and sentence embedding, and making us have a more comprehensive understanding about these embeddings.

### Why it worth to explore this question？

Although there are several papers declare they have good result to make embedding, there are so many works to compare them.

### What challenge for this question

Choosing what kinds of tasks to evaluate these embedding.

### Solution idea in this work

They explore the embeddings through 4 kinds of different tasks:

1. Downstream classification tasks
2. Semantic relatedness and textual similarity tasks
3. Information retrieval tasks
4. Linguistic probing tasks

You can check detail tasks from the paper.

#### Result

They find there is no a technique can do best on all kinds of tasks, and everyone has its own bais.

1. For classification tasks, it seems ELMo do the best, and then InferSent and USE(Transformer).
2. For second kind of tasks, USE achieve the best on almost tasks except one, for which InferSent achieve the best.
3. For Linguisti probing tasks, ELMo achieve the best on almost tasks again.
4. For information retrieval tasks, it is InferSent achieve the best on almost tasks.

#### 