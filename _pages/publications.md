---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

<font size=5>**[OmniSafe: An Infrastructure for Accelerating Safe Reinforcement Learning Research](https://arxiv.org/pdf/2305.09304)**</font>

This paper is about to submit to JMLR.

[Download paper here](https://arxiv.org/pdf/2305.09304.pdf)

If you find OmniSafe useful or use OmniSafe in your research, please cite it in your publications.

```bibtex
@article{omnisafe,
  title   = {OmniSafe: An Infrastructure for Accelerating Safe Reinforcement Learning Research},
  author  = {Jiaming Ji, Jiayi Zhou, Borong Zhang, Juntao Dai, Xuehai Pan, Ruiyang Sun, Weidong Huang, Yiran Geng, Mickel Liu, Yaodong Yang},
  journal = {arXiv preprint arXiv:2305.09304},
  year    = {2023}
}
```



## Abstract

AI systems empowered by reinforcement learning (RL) algorithms harbor the immense potential to catalyze societal advancement, yet their deployment is often impeded by significant safety concerns. Particularly in safety-critical applications, researchers have raised concerns about unintended harms or unsafe behaviors of unaligned RL agents. The philosophy of safe reinforcement learning (SafeRL) is to align RL agents with harmless intentions and safe behavioral patterns. In SafeRL, agents learn to develop optimal policies by receiving feedback from the environment, while also fulfilling the requirement of minimizing the risk of unintended harm or unsafe behavior. However, due to the intricate nature of SafeRL algorithm implementation, combining methodologies across various domains presents a formidable challenge. This had led to an absence of a cohesive and efficacious learning framework within the contemporary SafeRL research milieu. In this work, we introduce a foundational framework designed to expedite SafeRL research endeavors. Our comprehensive framework encompasses an array of algorithms spanning different RL domains and places heavy emphasis on safety elements. Our efforts are to make the SafeRL-related research process more streamlined and efficient, therefore facilitating further research in AI safety. Our project is released at: [this https URL](https://github.com/PKU-Alignment/omnisafe).
