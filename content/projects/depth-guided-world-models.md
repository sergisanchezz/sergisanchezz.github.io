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

The aim of the project is to inject geometric information into a self-supervised visual representation learning pipeline by integrating depth signals into the process. We explored different strategies to guide the representation learning, using depth prediction as an auxiliary task or via a feature-level guidance strategy. Specifically, the training pipeline for I-JEPA (Image Joint Embedding Predictive Architecture) was augmented with depth supervision signals. The resulting model learns to predict target patches from given context patches while simultaneously being supervised by ground-truth depth maps. The research involved analyzing the trade-offs of different masking strategies and supervision signals, concluding that the approach is a promising direction for creating robust and geometrically-aware world models for scene prediction in autonomous vehicles.