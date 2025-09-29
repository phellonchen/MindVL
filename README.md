# MindVL
MindVL: Towards Efficient and Effective Training of Multimodal Large Language Models on Ascend NPUs

## Abstract
We propose \textbf{MindVL}, a multimodal large language model (MLLMs) trained on Ascend NPUs. The training of state-of-the-art MLLMs is often confined to a limited set of hardware platforms and relies heavily on massive, undisclosed data recipes, which hinders reproducibility and open research. To change the common perception that Ascend hardware is unsuitable for efficient full-stage MLLM training, we introduce \textbf{MindSpeed-MLLM}, a highly efficient training framework that supports stable and high-performance training of large-scale Dense and Mixture-of-Experts (MoE) models on Ascend hardware. Based on this, we provide a systematic and open description of the data production methods and mixing strategies for all training stages. Furthermore, we present MindVL, a data-efficient multimodal large language model trained end-to-end on Ascend NPUs. In addition, we find that averaging weights from checkpoints trained with different sequence lengths is particularly effective and yields further gains when combined with test-time resolution search. Our experiments demonstrate superior data efficiency: \textbf{MindVL-8B} matches the performance of Qwen2.5VL-7B using only 10\% of its training data, while our MoE model, \textbf{MindVL-671B-A37B}, matches Qwen2.5VL-72B using only 3\% of the Qwen2.5VL training data, and achieves comparable performance with other leading multimodal MoE models. Our work provides the community with a valuable hardware alternative, open data recipes, and effective performance-enhancing techniques.

<p align="center">
    <img src="images/benchmark.png" width="70%"> <br>
    Benchmark performance of MindVL and its counterparts.
</p>

## Overview of MindSpeed-MLLM

<p align="center">
    <img src="images/mllm_figure.jpg" width="80%"> <br>
    The Overall Architecture of MindSpeed-MLLM and Its Relationship with Other MindSpeed Frameworks.
</p>


If you find MindVL useful for your research and applications, please cite using this BibTeX:
```
@article{chen2025mindvl,
  title={MindVL: Towards Efficient and Effective Training of Multimodal Large Language Models on Ascend NPUs},
  author={Chen, Feilong and Liu, Yijiang and Huang, Yi and Wang, Hao and Tian, Miren and Yu, Ya-Qi and Liao, Minghui and Wu, Jihao},
  journal={arXiv preprint arXiv:2509.11662},
  year={2025}
}
```
