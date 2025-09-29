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
    <img src="images/mllm_figure.jpg" width="70%"> <br>
    The Overall Architecture of MindSpeed-MLLM and Its Relationship with Other MindSpeed Frameworks.
</p>

## Comparison of OCR, chart, document and general understanding performance.
| Model                | #Tokens  | MME  | MMBench  | OCR Bench | DocVQA   | ChartQA  | InfoVQA  | Overall  |
|----------------------|----------|------|----------|-----------|----------|----------|----------|----------|
| GPT-4V               | --       | 68.8 | 80.0     | 64.5      | 88.4     | 78.5     | 75.1     | 70.0     |
| GPT-4o-20240513      | --       | --   | 83.1     | 73.6      | 92.8     | 85.7     | 79.2     | --       |
| Claude-3-Opus        | --       | 56.7 | 60.1     | 69.4      | 89.3     | 80.8     | 55.6     | 67.3     |
| Claude-3.5-Sonnet    | --       | --   | 80.9     | 78.8      | 95.2     | 90.8     | 74.3     | --       |
| Gemini-1.5-Pro       | --       | --   | 74.6     | 75.4      | 93.1     | 87.2     | 81.0     | --       |
| Step3V               | --       | --   | 81.1     | 83.7      | --       | --       | --       | --       |
| GLM-4.5V             | 2T+      | --   | 86.7     | 87.2      | 94.5     | 86.6     | 84.1     | 75.8     |
| Qwen2-VL-72B         | 1.4T+    | 88.7 | 85.9     | 87.7      | **96.5** | 88.3     | 84.5     | 88.6     |
| Qwen2.5-VL-72B       | 4.1T+    | 87.4 | <u>88.4</u> | <u>88.5</u> | <u>96.4</u> | <u>89.5</u> | <u>87.3</u> | 89.6     |
| InternVL3-78B        | 200B+    | **91.1** | 87.7     | <u>90.6</u> | 95.4     | **89.7** | 86.5     | <u>90.2</u> |
| InternVL3.5-241B-A28B| 380B+    | --   | 87.4     | **90.7**  | 94.9     | 88.0     | 82.0     | --       |
| MindVL-671B-A37B     | 106B     | **91.1** | **90.8** | 90.0      | 96.0     | 89.0     | **88.9** | **91.0** |

## Comparison of model performance across diverse language benchmarks. 
(All results are uniformly evaluated by the internal testing platform.)
| Model                | AIME2024 | AIME2025 | GPQA-D    | IFEval    | ArenaHard | C-SimpleQA | C-Eval    | Overall   |
|----------------------|----------|----------|-----------|-----------|-----------|------------|-----------|-----------|
| Qwen2.5VL-32B        | 30.0     | 16.7     | 51.5      | 64.3      | 92.2      | 44.9       | 81.3      | 54.1      |
| Qwen2.5VL-72B        | 26.7     | 16.7     | 50.0      | 85.6      | 71.2      | 49.8       | 86.1      | 55.2      |
| DeepSeek-V3-0324     | 60.0     | 43.3     | **69.2**  | 81.9      | 94.8      | **73.3**   | **89.6**  | 73.2      |
| MindVL-671B-A37B     | **63.3** | **46.7** | 68.7      | **84.7**  | **97.0**  | 72.9       | 88.2      | **74.5**  |


## Citation
If you find MindVL useful for your research and applications, please cite using this BibTeX:
```
@article{chen2025mindvl,
  title={MindVL: Towards Efficient and Effective Training of Multimodal Large Language Models on Ascend NPUs},
  author={Chen, Feilong and Liu, Yijiang and Huang, Yi and Wang, Hao and Tian, Miren and Yu, Ya-Qi and Liao, Minghui and Wu, Jihao},
  journal={arXiv preprint arXiv:2509.11662},
  year={2025}
}
```
