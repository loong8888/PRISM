# PRISM: Prior-Rich Single-Image Animatable Avatar via Synergistic Multi-Source Knowledge Supervision

[Paper](#) | [Project Page](#) | [Code](#)

## Overview

PRISM is a framework for reconstructing animatable 3D human avatars from a single image. By synergizing multi-source supervision, it achieves robust novel view synthesis and high-quality geometry reconstruction.

---

## Requirements

```bash
# Python 3.10+, CUDA 12.0+
pip install -r requirements.txt
```

Key dependencies:
- PyTorch ≥ 2.80
- [pytorch3d](https://github.com/facebookresearch/pytorch3d)
- [smplx](https://github.com/vchoutas/smplx)
- [diffusers](https://github.com/huggingface/diffusers)

---

## 🚀 News
- **[TODO]** Release pre-trained weights and demo scripts.
- **[TODO]** Release training and evaluation code.


## 🛠️ Installation

Create a conda environment and install the required dependencies:

```bash
conda create -n prism python=3.10
conda activate prism

# Install PyTorch (Modify according to your CUDA version)
conda install pytorch torchvision torchaudio pytorch-cuda=12.8 -c pytorch -c nvidia

# Install other requirements
pip install -r requirements.txt
```

## 📊 Data Preparation

We evaluate our method on the **NeuMan** and **X-Humans** datasets. Please download the datasets from their official websites and organize them as follows:

```text
data/
├── neuman/
│   ├── subject_1/
│   ├── subject_2/
│   └── ...
└── xhumans/
    ├── ...
```

## 💻 Usage

### Training

To train the PRISM model from scratch on a specific subject, run:

```bash
python train.py --config configs/neuman.yaml --subject subject_1
```

### Evaluation / Animation

To render novel views or animate the avatar with novel poses using a pre-trained model:

```bash
# Novel view synthesis
python evaluate.py --config configs/neuman.yaml --subject subject_1 --checkpoint path/to/ckpt

# Animation with novel poses
python animate.py --config configs/neuman.yaml --subject subject_1 --pose_sequence path/to/poses
```


## License

This project is released under the [MIT License](LICENSE).

## Acknowledgements

We thank the authors of [SMPL-X](https://smpl-x.is.tue.mpg.de/), [NeuMan](https://github.com/apple/ml-neuman), and [X-Humans](https://skype-line.github.io/projects/X-Humans/), [PERSONA](https://github.com/mks0601/PERSONA_RELEASE), [MimicMotion](https://github.com/Tencent/MimicMotion), [2D Gaussian Splatting](https://github.com/hbb1/2d-gaussian-splatting), [SyncHuman](https://github.com/IGL-HKUST/SyncHuman) for their excellent work and datasets.
