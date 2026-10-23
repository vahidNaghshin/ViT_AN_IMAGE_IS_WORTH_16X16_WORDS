# Implementation of 'An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale' (ViT)

This repository contains a clean, PyTorch-based implementation of the Vision Transformer (ViT) architecture, as introduced in the seminal ICLR 2021 paper, "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale" by Alexey Dosovitskiy et al. (Google Research).

This project makes the paper's main concepts concrete, specifically illustrating the process of image tokenization, embedding, and the application of a standard Transformer Encoder for image classification.

## Project Goal and Key Concepts

The primary goal of this implementation is to demonstrate the ViT architecture's capability to learn powerful image representations by treating an image as a sequence of patches, leveraging the scaling properties of Transformers.

This repository focuses on demonstrating key ViT concepts through code and associated diagrams:

*   **Image Tokenization (Patch Embedding):** How a 2D image is divided into a grid of non-overlapping patches and projected into a shared linear embedding space.
*   **The Embedding Space Geometry:** Visualizing how the linear projection organizes the embedded patches based on content, establishing initial spatial/semantic relationships before attention.
*   **Transformer Encoder block structure:** Disentangling the roles of Query (Q), Key (K), and Value (V) in multi-head self-attention and showing the data flow through residual additions and the MLP.
*   **Final Attention Map Visualizations:** Showing how the final layer's attention (specifically from the `[CLS]` token) naturally focuses on semantically meaningful objects without explicit supervision.
*   **Visualizing Architectural Differences:** Contrasting the local, hierarchical nature of CNN feature extraction with the global, data-driven patch relationships in ViT from the first layer.

## Pre-training and Scaling Analysis

This implementation includes scripts for pre-training and allows for testing the scalability claims of the ViT paper on different dataset sizes:

*   **Small datasets (limited inductive bias):** Demonstrating the advantage of CNNs' inductive biases and the challenge of scaling ViT without enough data.
*   **Medium/Large scale pre-training:** Visually illustrating the "crossover point" where ViT scales more effectively than CNN baselines when sufficient data (e.g., JFT-300M, or an ImageNet-21k proxy) is provided.

## How it Fits into the Transformer Ecosystem

This repository situates the ViT paper at a crucial historical inflection point (circa 2020), demonstrating how it opened the door for self-supervised ViT variants, hierarchical architectures (e.g., Swin), and vision-language models like CLIP and subsequent multimodal large models.

## Usage and Citations

### Prerequisite Codebase

This code is based on the official ViT repository: `github.com/google-research/vision_transformer` and uses the pretrained `ViT-B/16` checkpoint for demo scripts.

### Citation

If you use this codebase or find the provided conceptual visualizations helpful, please cite the original ViT paper:

```latex
@article{dosovitskiy2020vit,
  title={An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale},
  author={Dosovitskiy, Alexey and Beyer, Lucas and Kolesnikov, Alexander and Weissenborn, Dirk and Zhai, Xiaohua and Unterthiner, Thomas and Dehghani, Mostafa and Minderer, Matthias and Heigold, Georg and Gelly, Sylvain and others},
  journal={arXiv preprint arXiv:2010.11929},
  year={2020}
}
