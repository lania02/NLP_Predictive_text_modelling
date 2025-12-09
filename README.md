# NLP Predictive Text Modelling with LSTM

This project focuses on **predictive text modelling**, a core application in Natural Language Processing (NLP) used in systems such as autocorrect, autocomplete, and dialogue generation. The objective is to solve a **two-word / two-letter autocompletion task** using a **Long Short-Term Memory (LSTM)** based language model.

The model is trained on a small corpus of **modern English novels from the Gutenberg Project**.

---

## Background

### Recurrent Neural Networks (RNN)
Recurrent Neural Networks (RNNs) are designed to handle sequential data by maintaining a hidden state that captures previous information. However, traditional RNNs suffer from:
- **Vanishing gradients**
- **Exploding gradients**

These issues limit their ability to learn long-term dependencies.

### Long Short-Term Memory (LSTM)
LSTM networks improve upon RNNs by introducing:
- **Memory cells**
- **Input, Output, and Forget gates**

This structure allows LSTMs to retain important information over long sequences, making them particularly effective for **language modelling and text prediction**.

### Gated Recurrent Unit (GRU)
GRU is a simplified alternative to LSTM:
- Combines input and forget gates into an **update gate**
- Merges cell state and hidden state
- Trains faster with comparable performance in many tasks

In this project, **LSTM was selected** due to its stronger performance on tasks with **longer and more complex dependencies**.

---

## Dataset Limitations

The dataset consists of:
- **10 novels from Project Gutenberg**
- Mostly **pre-21st century literature**
- Multiple works from the same author (e.g. Shakespeare)

This introduces several limitations:
- Limited relevance to **modern English usage**
- **Stylistic bias** due to repeated authors
- Reduced **generalisability**

---

## Model and Data Size Mismatch

A key challenge in this project is the imbalance between:
- **Model complexity**
- **Small training corpus**

This leads to:
- **Overfitting** in more complex models (observed in Model-2)
- **Underfitting** in simpler models

Overall, the dataset size is **insufficient for optimal performance** with deep models like LSTM.

---

## Evaluation Insights

Model performance was primarily evaluated using **perplexity**, but several issues were discovered:

- **Model-3** achieved the *best perplexity*
- **Model-2**, despite having the *worst perplexity*, produced the **most reasonable real-world predictions**
- Vocabulary sizes differed drastically:
  - Smaller vocabulary → Lower perplexity
  - Larger vocabulary → Better real-world expressiveness

This highlights that:
> **Perplexity alone is not a sufficient evaluation metric for practical predictive text performance.**

Longer tokens often embed more syntactic information, improving real-world prediction quality even if perplexity increases.

---

## Conclusion

- LSTM is well-suited for predictive text modelling with long dependencies
- Dataset limitations significantly constrain performance
- Model complexity must be balanced with corpus size
- Perplexity should be combined with **qualitative evaluation** for realistic assessment

---

## Future Improvements

- Expand the corpus with **modern, diverse text**
- Test hybrid evaluations beyond perplexity
- Compare LSTM with transformer-based models
- Improve generalisation through regularisation and data augmentation
