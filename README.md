# GenSE: Generative Speech Enhancement via Language Models using Hierarchical Modeling <br> <sub>The official implementation of GenSE submitted to ICLR 2025 </sub>

We propose a comprehensive framework tailored for language model-based speech enhancement, called GenSE. Speech enhancement is regarded as a conditional language modeling task rather than a continuous signal regression problem defined in existing works. This is achieved by tokenizing speech signals into semantic tokens using a pre-trained self-supervised model and into acoustic tokens using a custom-designed single-quantizer neural codec model. 

<p align="center">
  <img src="fig/gense.png" width="600"/>
</p>

GenSE employs a hierarchical modeling framework with a two-stage process: a N2S transformation front-end, which converts noisy speech into clean semantic tokens, and an S2S generation back-end, which synthesizes clean speech using both semantic tokens and noisy acoustic tokens.

## TODO 📝
- [x] Release Inference pipeline
- [ ] Release pretrained model
- [ ] Support in colab
- [ ] More to be added

## Getting Started 📥

### 1. Pre-requisites
0. Pytorch >=1.13 and torchaudio >= 0.13
1. Install requirements
```
conda create -n gense python=3.8
pip install -r requirements.txt
```

### 2. Get Self-supervised Model:
Download [XLSR model](https://huggingface.co/facebook/wav2vec2-xls-r-300m)  and move it to ckpts dir.

### 3. Pre-trained Model:
We will release pre-trained model soon.

### 4. Inference:
```
python infer.py run \
  --noisy_path noisy.wav 
  --out_path ./enhanced.wav 
  --config_path configs/gense.yaml
```
