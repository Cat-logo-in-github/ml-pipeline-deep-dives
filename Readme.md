# ML Pipeline Deep Dives

> **Exploring advanced machine learning pipelines through real-world problems, research implementations, and competition systems.**

This repository is a collection of **deep dives into interesting machine learning pipelines**.

The goal isn't to build another ML framework or collect isolated model implementations. Instead, this project is about taking complicated ML systems and **pulling them apart**:

* What problem is the pipeline actually solving?
* Why is the pipeline structured the way it is?
* What happens to the data at every stage?
* Why were particular architectures chosen?
* How do seemingly independent models fit together?
* Where does training happen?
* How does information flow through the system?
* What are the important engineering and modeling decisions?
* Could the same ideas be applied somewhere else?

The emphasis is on understanding the **whole pipeline**, rather than just studying the final model.

---

## What is a "deep dive"?

Modern ML systems are rarely just:

```text
data → model → prediction
```

Interesting systems often look more like:

```text
Raw Data
   ↓
Preprocessing
   ↓
Representation / Feature Extraction
   ↓
Intermediate Model
   ↓
Structured Representation
   ↓
Another Model
   ↓
Post-processing
   ↓
Final Prediction
```

And sometimes several of these stages interact in non-obvious ways.

This repository explores those systems **stage by stage**.

For each pipeline, the aim is to understand both the **machine learning concepts** and the **engineering decisions** that make the complete system work.

---

# Current Deep Dives

## 🧬 Biohub Kaggle Competition Pipeline

**Problem:** Cell tracking and lineage reconstruction in 3D microscopy.

This deep dive explores a pipeline designed for the **Biohub Kaggle competition**, where the objective is to detect, track, and link cells across time in 3D microscopy data, including identifying cell divisions and reconstructing cell lineages.

### Pipeline

```text
3D Microscopy Volumes
        │
        ▼
Image Preprocessing
        │
        ▼
Temporal U-Net
        │
        ▼
Dense Voxel Feature Maps
        │
        ▼
Node / Cell Features
        │
        ▼
Simple Node Transformer
        │
        ▼
Graph Construction
        │
        ▼
Edge Prediction
        │
        ▼
Cell Tracking / Lineage
```

The deep dive currently explores components including:

* **Image preprocessing**
* **Temporal U-Net**
* **Dense voxel feature maps**
* **Node feature construction**
* **Transformer-based node processing**
* **Graph construction**
* **Edge prediction**
* **End-to-end pipeline behaviour**

The project also includes an introductory exploration of the `.zarr` and `.geff` data formats used by the competition.

### Explore the deep dive

👉 **[Read the Biohub Kaggle Competition Pipeline](https://cat-logo-in-github.github.io/ml-pipeline-deep-dives/biohub-kaggle-competition-pipeline/)**

The repository breaks the pipeline into smaller explorations:

```text
modules/
└── biohub-kaggle-competition-pipeline/
    ├── image-preprocessing/
    ├── temporal-unet/
    ├── simple-node-transformer/
    ├── graph-construction/
    └── complete-pipeline-analysis/
```

---

# What I'm Exploring

Future deep dives will focus on pipelines where the interesting part isn't simply the architecture, but **how multiple ideas are composed into a working system**.

Areas of interest include:

### Computer Vision

* 3D vision
* Video understanding
* Object tracking
* Segmentation pipelines
* Multi-stage detection systems
* Vision transformers
* Medical and scientific imaging

### Graph Machine Learning

* Graph neural networks
* Dynamic graphs
* Graph construction
* Node and edge prediction
* Temporal graph learning
* Graph transformers

### Sequence & Temporal Modeling

* Temporal CNNs
* Transformers
* State-space models
* Video models
* Long-context architectures
* Multi-frame prediction

### Scientific Machine Learning

* Biology
* Microscopy
* Molecular modelling
* Physics-inspired ML
* Scientific competitions
* ML systems built around scientific datasets

### Competition & Research Pipelines

A particular interest is understanding **strong competition and research solutions**.

Rather than only asking:

> "What model did they use?"

the deeper questions are:

> "Why does this pipeline work?"

and:

> "How do all of these components interact?"

---

# How These Deep Dives Work

Each investigation tries to move through several levels of understanding.

### 1. Understand the Problem

Before looking at the model, understand what the system is actually trying to predict.

```text
Real-world problem
       ↓
ML formulation
       ↓
Prediction target
```

### 2. Understand the Data

What does the raw data look like?

How is it represented?

What information is available during training versus inference?

What preprocessing is required?

```text
Raw Dataset
    ↓
File Formats
    ↓
Samples
    ↓
Features / Labels
    ↓
Model Inputs
```

### 3. Trace the Pipeline

Follow the data through the entire system.

```text
Input
 ↓
Preprocessing
 ↓
Model A
 ↓
Intermediate Representation
 ↓
Model B
 ↓
Structured Output
 ↓
Final Prediction
```

### 4. Understand Individual Components

Each major component gets its own investigation where useful.

For example:

```text
Temporal U-Net
     ↓
What problem does it solve?
     ↓
What goes into it?
     ↓
What comes out?
     ↓
Why U-Net?
     ↓
Why temporal information?
```

### 5. Reconstruct the Full System

Individual components only become meaningful when they are connected.

The final stage is therefore to reconstruct the complete pipeline and understand the information flow from input to output.

---

# Repository Structure

The repository separates the **pipeline investigations** from the generated/published website.

```text
ml-pipeline-deep-dives/
│
├── modules/
│       ├── <pipeline>/
│       ├── <component>/
│       ├── <component>/
│       └── complete-pipeline-analysis/
│
├── website/
│   └── ...
│
├── Readme.md
├── pyproject.toml
└── requirements.txt
```
The current structure is inefficient but because currently it has 1 pipeline only, improvements were not required. Atlas v2.0 should use a more efficient structure (not out yet)

The `modules/` directory contains the actual research/deep-dive material, while `website/` contains the published presentation of that material.

The published site is generated using Quartz and is available here:

👉 **[ML Pipeline Deep Dives — Website](https://cat-logo-in-github.github.io/ml-pipeline-deep-dives/)**

---

# Current Status

🚧 **Early stage / actively expanding**

Currently, the repository contains **one complete pipeline investigation**:

* 🧬 Biohub Kaggle Competition Pipeline

The intention is for this repository to grow into a collection of progressively more interesting ML systems.

Each new deep dive will ideally add another example of a fundamentally different pipeline design.

---

# Why This Repository Exists

Machine learning tutorials often isolate concepts:

```text
CNN
Transformer
GNN
U-Net
Attention
```

Those concepts are useful, but real ML systems rarely use them in isolation.

A production or competition pipeline might combine:

```text
Computer Vision
      +
Temporal Modeling
      +
Transformers
      +
Graph Construction
      +
Graph Prediction
      +
Post-processing
```

The interesting engineering happens **between the boxes**.

This repository exists to explore those connections.

> **Don't just learn the model. Understand the pipeline.**

---

# Roadmap

The repository will gradually expand into deeper and more varied ML systems.

Possible future investigations include:

* [ ] More computer vision pipelines
* [ ] More graph ML pipelines
* [ ] Multimodal ML systems
* [ ] Long-context / sequence pipelines
* [ ] Scientific ML systems
* [ ] Interesting Kaggle solutions
* [ ] Research-paper implementations
* [ ] Production ML architectures
* [ ] Comparisons between alternative pipeline designs
* [ ] End-to-end visualizations of complex pipelines

The roadmap is intentionally open-ended. The main criterion for adding a pipeline is simple:

**Is there something interesting to learn by taking it apart?**

---

# Contributing

This is primarily a personal exploration/research repository, but interesting pipelines, papers, competitions, implementations, or ideas for future deep dives are welcome.

If you find a particularly interesting ML system that would be worth dissecting, feel free to open an issue or discussion.

---

# License

MIT
