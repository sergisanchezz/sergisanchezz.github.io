---
title: "Event-based Egomotion Estimation"
start_date: "2023-09-01"
end_date: "2024-06-01"
affiliations:
  - name: "Universitat Politècnica de Catalunya (UPC)"
    url: "https://www.upc.edu/en"
  - name: "IRI-CSIC"
    url: "https://www.iri.upc.edu/"
authors: ["Sergi Sánchez Orvay"]
supervisors: ["Dr. Juan Andrade-Cetto"]
github_link: "" # Add link here if available
report_link: "/files/Event-based_egomotion_estimation_Sergi_Sanchez_Orvay_TFG.pdf" # Link to the uploaded file
draft: false
layout: "project_single"
---

**Event cameras** are bio-inspired sensors that detect logarithmic changes in pixel-level illumination, generating events asynchronously with microsecond resolution. This principle provides significant advantages over conventional cameras such as high dynamic range, low latency, and low power consumption, making them ideal for dynamic scenarios and challenging lighting conditions. This work addresses the **egomotion estimation** of an event camera using a geometric model-based approach and optimization techniques, avoiding the use of learning methods to make it applicable in resource-constrained environments and to deeply understand the problem. The proposed methodology consists of three main blocks: **normal flow estimation**, **inverse depth estimation**, and a **robust linear solver**. The normal flow estimation method is based on fitting local planes on **Surfaces of Active Events (SAEs)**, while inverse depth is tackled using optimization techniques to align events at a reference timestamp (contrast maximization approach). Finally, a robust linear solver based on the iterative **RANSAC** method is implemented, using the inverse depth and normal flow estimates to obtain the camera's linear velocity. The method's performance is evaluated through experiments with synthetic and real data.