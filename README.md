# Musical Sparse Attention transformer with RoPE embeddings

**Overview:** A model that generates pieces of classical piano music in a midi format.

- This is my first stepping stone, a Hierarchical VQ-VAE transformer for advanced music generation.
- This model has 85 million parameters and was trained on the “Maestro piano midi” dataset from Kaggle for 640000 iterations on A100 GPU
- Overall, the model follows a standard Multihead decoder-only architecture (similar to GPT2), but it introduces RoPE embeddings and Sparse Attention for more tailored processing of musical structure and uses “Midi Neural Processor” library to convert midi into tokens.
- RoPE allows to produce embeddings that contain meaningful information about the relative positioning of tokens and how close they are, allowing the Transformer model to focus more on the immediate neighbourhoods of each token, providing more melodic results.
- Sparse attention is a modification to the attention mask that allows restricting the number of tokens that the model can attend to, in our cause we attend to the local neighbourhood of each token and some periodic positions - reflecting the local and repetitive structure of the music.

## Links for the model:

Model notebook on Kaggle: [link](https://www.kaggle.com/code/kyrylodegtiarenko/midi-generation)

Model weights: [link](https://www.kaggle.com/datasets/kyrylodegtiarenko/midi-sparse-rope-transformer-files)
