---
title: "Towards Depth-Guided Self-Supervised World Models"
start_date: "2025-02-01"
end_date: "2025-07-01"
affiliations:
  - name: "ETH Zürich"
    url: "https://ethz.ch/"
authors: ["Juan Tarazona Rodríguez", "Ahmed Elgaradiny", "Hanqiu Li Cai", "Sergi Sánchez Orvay"]
supervisors: ["Mirlan Karimov"]  # Optional field, leaving empty or commenting out
github_link: "https://github.com/Juan5713/MM_WM_AD" # Add link here if available
report_link: "/files/3DV_Report.pdf" # Link to the uploaded file
draft: false
layout: "project_single"
---

In recent years there have been significant advancements in the field of autonomous driving, led by improvements in perception, planning and control systems. Modern autonomous vehicles rely on complex sensor suites including cameras and LiDAR scanners to interpret their surroundings and make real-time decisions. A current major challenge lies in predicting future scenes, which is crucial to enable safe and reliable navigation.

Recent research trends in autonomous driving explore the usage of world models to perform the prediction of such future scenes. These models take in sensor inputs from a number of frames in the past and infers the scene and trajectory of the ego vehicle for the next frames. Current state-ofthe- art (SOTA) world models leverage different representations of the scene to perform this task, leading to the following pipeline categories:

* Image-based These models leverage RGB data from cameras. Their main limitation lies in the inability to fully capture the details of the 3D environment.

* BEV-based Bird’s-Eye view (BEV) converts multimodal sensor data into a top-down view in 2D. These models suffer from difficulty capturing fine-grained 3D geometries in certain scenarios.

* OG-based Occupancy grids (OG) discretize the environment into a voxel grid, encoding high-fidelity 3D spatial information. The main limitation lies in the large memory and computational requirements.

* PC-based PC (Point Cloud) based models use 3D scanning data from LiDAR sensors. Despite their precision, these models are computationally intensive due to data sparsity and high input dimensionality.

However, all these approaches treat geometry and appearance
separately, potentially limiting their ability to
capture the full complexity of driving environments.

The original project proposal aimed to develop a unified multimodal world model modelled by a spatio-temporal transformer or a diffusion model that jointly predicts both point clouds and video frames. However, after the initial literature review phase on the topic, it was concluded that such a model would be infeasible to train given the limited compute available to us and short timeframe of the course. Hence, it was decided that we would shift our focus towards improving existing self-supervised representation learning methods from RGB images by enhancing them with depth guidance, thus enabling them to encode implicit 3D information in their features.

As a baseline, we used I-JEPA (Image Joint Embedding Predictive Architecture), a self-supervised learning method that predicts masked regions in latent space, enabling the model to learn high-level semantics rather than pixel-level details. This has shown significant improvements in downstream tasks that require structural understanding of the scene, such as in autonomous driving. We explored two methods of adding depth guidance to I-JEPA’s training: pixel-level guidance with ground truth metric labels,
and feature-level guidance via latent representations from a SOTA monocular depth estimation model (DepthFM).