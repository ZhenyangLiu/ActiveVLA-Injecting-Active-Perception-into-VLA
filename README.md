# ActiveVLA: Injecting Active Perception into Vision-Language-Action Models for Precise 3D Robotic Manipulation

<div align="center">

**Zhenyang Liu**<sup>1,2</sup>, **Yongchong Gu**<sup>1</sup>, **Yikai Wang**<sup>3,*</sup>,  
**Xiangyang Xue**<sup>1,†</sup>, **Yanwei Fu**<sup>1,2,†</sup>

<sup>1</sup>Fudan University, <sup>2</sup>Shanghai Innovation Institute, <sup>3</sup>Nanyang Technological University

<sup>*</sup>Corresponding Author, <sup>†</sup>Co-corresponding Authors

[![Paper](https://img.shields.io/badge/Paper-Arxiv-b31b1b.svg)](https://arxiv.org/abs/2601.08325v1)
[![Project Page](https://img.shields.io/badge/Project-Website-blue.svg)](https://zhenyangliu.github.io/ActiveVLA/)
[![Video](https://img.shields.io/badge/Video-YouTube-red.svg)](https://zhenyangliu.github.io/ActiveVLA)

</div>

---

## 📢 News & Roadmap

This repository is the official implementation of **ActiveVLA**. We are currently preparing the code and data for release. Please stay tuned!

- [ ] **Release the Code** (Training & Inference scripts).
- [ ] **Release Pre-trained Models**.
- [ ] **Release Evaluation Scripts** (RLBench, COLOSSEUM, GemBench).
- [ ] **Release Real-Robot Control Code**.

---

## 📖 Abstract

Most existing Vision-Language-Action (VLA) models rely on static, wrist-mounted cameras that provide a fixed, end-effector-centric viewpoint. This setup limits perceptual flexibility: the agent cannot adaptively adjust its viewpoint or camera resolution according to the task context, leading to failures in long-horizon tasks or fine-grained manipulation due to occlusion and lack of detail.

We propose **ActiveVLA**, a novel vision-language-action framework that explicitly integrates **active perception** into robotic manipulation. Unlike passive perception methods, ActiveVLA empowers robots to:
1.  **Actively Select Viewpoints:** Autonomously determine optimal camera perspectives to maximize visibility and task relevance while minimizing occlusions.
2.  **Active 3D Zoom-in:** Selectively enhance high-resolution views of task-critical regions within the 3D scene.

By dynamically refining its perceptual input, ActiveVLA achieves superior adaptability and performance in complex scenarios. Experiments show that ActiveVLA outperforms state-of-the-art baselines on **RLBench**, **COLOSSEUM**, and **GemBench**, and transfers seamlessly to real-world robots.

<div align="center">
  <img src="assets/teaser.png" width="90%">
  <br>
  <em>Figure 1: Comparison between previous VLA methods and ActiveVLA. While traditional VLAs fail due to fixed cameras and occlusion (left), ActiveVLA leverages 3D scene understanding to actively select better views and observe more carefully (right).</em>
</div>

---

## 🚀 Method: ActiveVLA

We propose a coarse-to-fine active perception framework that integrates 3D spatial reasoning with vision-language understanding.

The pipeline consists of two main stages:
1.  **Critical Region Localization (Coarse Stage):** Projects 3D inputs onto multi-view 2D projections to identify critical 3D regions via heatmaps.
2.  **Active Perception Optimization (Fine Stage):**
    *   **Active Viewpoint Selection:** Uses a hypothesis testing strategy to choose optimal viewpoints that maximize amodal relevance and diversity.
    *   **Active 3D Zoom-in:** Applies a virtual optical zoom effect to improve resolution in key areas for precise manipulation.

<div align="center">
  <img src="assets/pipeline.png" width="100%">
  <br>
  <em>Figure 2: The pipeline of ActiveVLA. It adopts a two-stage strategy involving coarse heatmap prediction followed by active view selection and 3D zoom-in to generate the final 3D action.</em>
</div>

> **Note:** For more visualizations and real-world robot demos, please visit our [**Project Page**](https://zhenyangliu.github.io/ActiveVLA).

---

## 📊 Results

ActiveVLA achieves state-of-the-art performance across multiple benchmarks:

- **RLBench:** Achieves an average success rate of **91.8%**, ranking 1st in 10 tasks.
- **COLOSSEUM:** Demonstrates superior robustness with a **65.9%** success rate in challenging generalization scenarios.
- **GemBench:** Outperforms all baselines with strong adaptability across diverse tasks.
- **Real World:** High success rates in occlusion-heavy tasks (e.g., retrieving items from drawers, handling occluded objects).

---

## 📝 Citation

If you find our work useful in your research, please consider citing:

```bibtex
@misc{liu2026activevlainjectingactiveperception,
      title={ActiveVLA: Injecting Active Perception into Vision-Language-Action Models for Precise 3D Robotic Manipulation}, 
      author={Zhenyang Liu and Yongchong Gu and Yikai Wang and Xiangyang Xue and Yanwei Fu},
      year={2026},
      eprint={2601.08325},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2601.08325}, 
}
