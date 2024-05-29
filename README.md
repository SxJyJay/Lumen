# Lumen: Unleashing Versatile Vision-Centric Capabilities of Large Multimodal Models

<font size=7><div align='center'><b>Lumen</b>: <b>L</b>arge m<b>u</b>ltimodal <b>m</b>odel with versatile vision-centric capabilities <b>en</b>hancement</div></font>

## News
- [x] [2024.5.30] Upgraded version of [Lumen-v1.5](https://arxiv.org/abs/2403.07304) is introduced. Lumen-v1.5 extends versatile vision-centric capabilities while maintaining general-purpose conversational capabilities.
- [x] [2024.3.13] Lumen [paper](https://arxiv.org/abs/2403.07304) is released on the arxiv.
- [x] [2024.3.12] Lumen GitHub repo is created.

**Lumen: Unleashing Versatile Vision-centric Capabilities of [[Paper](https://arxiv.org/abs/2403.07304)]** <br />
[Yang Jiao](https://scholar.google.com/citations?user=5gA7Wv0AAAAJ&hl=zh-CN),
[Shaoxiang Chen](https://scholar.google.com/citations?user=WL5mbfEAAAAJ&hl=zh-CN),
[Zequn Jie](https://scholar.google.com/citations?user=4sKGNB0AAAAJ&hl=zh-CN&oi=sra),
[Jingjing Chen](https://scholar.google.com/citations?user=DfWdqzQAAAAJ&hl=zh-CN),
[Lin Ma](https://scholar.google.com/citations?user=DAn1pA4AAAAJ&hl=zh-CN),
[Yu-Gang Jiang](https://scholar.google.com.hk/citations?user=BUEDUFkAAAAJ&hl=zh-CN)<br />

## Abstract
Large Multimodal Model (LMM) is a hot research topic in the computer vision area and has also demonstrated remarkable potential across multiple disciplinary fields. A recent trend is to further extend and enhance the perception capabilities of LMMs. The current methods follow the paradigm of adapting the visual task outputs to the format of the language model, which is the main component of a LMM. This adaptation leads to convenient development of such LMMs with minimal modifications, however, it overlooks the intrinsic characteristics of diverse visual tasks and hinders the learning of perception capabilities. To address this issue, we propose a novel LMM architecture named Lumen, a Large multimodal model with versatile vision-centric capability enhancement. We decouple the LMM's learning of perception capabilities into task-agnostic and task-specific stages. Lumen first promotes fine-grained vision-language concept alignment, which is the fundamental capability for various visual tasks. Thus the output of the task-agnostic stage is a shared representation for all the tasks we address in this paper. Then the task-specific decoding is carried out by flexibly routing the shared representation to lightweight task decoders with negligible training efforts.

## Performances
### Object Detection
| Type               | Model            | Input Size |  mAP  | AP50 | AP75 |
|--------------------|------------------|------------|------|------|------|
| Specialists        | Faster R-CNN-R50 | 1333*800   | 40.3 | 61.0 | 44.0 | 
|                    | DETR-DC5         | 1333*800   | 43.3 | 63.1 | 45.9 |
| Vision Generalists | Pix2Seq-v2       | 1024*1024  | 46.5 |   -  |  -  |
|                    | UniPerceiver-v2  | 1600*1400  | 58.6 |   -  |  -  |
| LMM Generalists    | Griffon-13B      | 448*448    | 24.8 | 40.6 | 25.1 |
|                    | **Lumen-7B**     | 448*448    | 33.9 | 51.2 | 34.2 |
|                    | **Lumen-7B-v1.5**| 448*448    | 35.3 | 53.2 | 35.8 |


### Instance Segmentation
| Type               | Model            |  mAP  | AP50 | AP75 |
|--------------------|------------------|------|------|------|
| Specialists        | Mask R-CNN-R50   | 37.1 | 58.4 | 40.1 | 
|                    | PolarMask        | 30.5 | 52.0 | 31.1 |
| Vision Generalists | Pix2Seq-v2       | 38.2 |   -  |  -  |
|                    | UniPerceiver-v2  | 50.6 |   -  |  -  |
| LMM Generalists    | **Lumen-7B**     | 29.1 | 47.5 | 29.6 |
|                    | **Lumen-7B-v1.5**| 30.4 | 49.8 | 31.0 |

### Pose Estimation
| Type               | Model            |  mAP  | AP50 | AP75 |
|--------------------|------------------|------|------|------|
| Specialists        | CPM              | 62.7 | 86.2 | 70.9 | 
|                    | RTMPose          | 68.2 | 88.3 | 75.9 |
| Vision Generalists | Pix2Seq-v2       | 64.8 |   -  |  -  |
| LMM Generalists    | **Lumen-7B**     | 65.4 | 90.4 | 72.2 |
|                    | **Lumen-7B-v1.5**| 67.2 | 90.4 | 75.6 |

### VQA
| Model              | EN_MMBench_DEV   |  SEED_IMG  |  MME     | MMMU_VAL | MathVista |
|--------------------|------------------|------------|----------|----------|-----------|
| InstructBLIP       | 36.0             | 58.8       | 1213/292 |  32.9    |    25.3   |
| MiniGPT-4          | 24.3             | 47.4       | 582/144  |  -       |    23.1   |
| Shikra             | 58.8             | -          | -        |  -       |    -      |
| Qwen-VL-Chat       | 60.6             | 58.2       | 1488/361 |  35.9    |    -      |
| LLaVA-v1.5         | 64.3             | 66.1       | 1511/296 |  35.6    |    23.5   |
| **Lumen-7B-v1.5**  | 64.9             | 65.8       | 1426/332 |  35.2    |    24.6   |

## Citation 
If you find this project useful in your research, please consider citing:

```
@article{jiao2024lumen,
  title={Lumen: Unleashing Versatile Vision-Centric Capabilities of Large Multimodal Models},
  author={Jiao, Yang and Chen, Shaoxiang and Jie, Zequn and Chen, Jingjing and Ma, Lin and Jiang, Yu-Gang},
  journal={arXiv preprint arXiv:2403.07304},
  year={2024}
}
```

## Acknowledgement
-  This work is built upon the [LLaVA](https://github.com/haotian-liu/LLaVA), [LISA](https://github.com/dvlab-research/LISA) and [SAM](https://github.com/facebookresearch/segment-anything). 
