# DR-MoEViT-UNet: Dynamically Routed Multi Task Mixture of Experts based Custom Vision Transformer and U-Net Network for Joint Colorectal Cancer Classification and Segmentation

## Project Overview

DR-MoEViT-UNet-CLS is a novel deep learning architecture for analyzing colorectal cancer histopathology images. The model performs simultaneous segmentation and classification of tissue samples, enabling both precise lesion delineation and accurate tissue type identification in a single unified framework.

## Key Contributions

- **Integration of Vision Transformers with Expert Systems**: We combine the global context understanding capabilities of transformers with specialized expert networks that focus on different aspects of histopathological features.

- **Dynamic Routing Mechanism**: Our approach implements an attention-based routing algorithm that adaptively selects the most relevant expert pathways based on the input characteristics, optimizing computational resources and improving feature extraction.

- **Multi-task Learning Framework**: The architecture simultaneously addresses segmentation and classification, allowing for knowledge sharing between these related tasks to improve overall performance.

- **Enhanced Segmentation Through U-Net Design**: We incorporate skip connections and progressive upsampling in a U-Net style decoder that preserves fine-grained spatial details critical for accurate lesion boundary delineation.

## Architecture Details

The DR-MoEViT-UNet-CLS architecture consists of the following key components:

### 1. Vision Transformer Encoder
- Divides input images into patches
- Applies self-attention mechanisms to capture long-range dependencies
- Generates contextualized feature representations

### 2. Mixture of Experts (MoE) Modules
- Multiple specialized expert networks
- Each expert focuses on different feature types and patterns
- Promotes specialization in the network

### 3. Dynamic Router
- Analyzes input features to determine routing weights
- Incorporates both spatial and channel attention mechanisms
- Enables conditional computation paths through the network

### 4. U-Net Decoder with Expert Integration
- Progressive upsampling of features
- Skip connections from the encoder to preserve spatial information
- Integration of expert outputs at multiple scales

### 5. Multi-task Heads
- Main classification head for tissue type identification
- Segmentation head for pixel-level mask prediction
- Auxiliary classification branches at different decoder levels

## Colorectal Tissue Classification

The model classifies tissue samples into six distinct categories:
- Adenocarcinoma
- High-grade Intraepithelial Neoplasia (IN)
- Low-grade Intraepithelial Neoplasia
- Normal tissue
- Polyp
- Serrated adenoma

## Loss Function Design

We implement a multi-component loss function that balances:
- Dice loss and Focal loss for segmentation accuracy
- Cross-entropy loss for classification performance
- Auxiliary losses to enhance gradient flow

## Visualization Capabilities

The architecture provides interpretability through:
- Attention map visualization from transformer layers
- Expert routing weight visualization showing the dynamic allocation of processing
- Overlay visualizations of segmentation predictions

## Dataset

The model is trained and evaluated on a colorectal cancer histopathology dataset with paired images and segmentation masks.

## Requirements

- PyTorch
- Vision libraries
- Image processing tools