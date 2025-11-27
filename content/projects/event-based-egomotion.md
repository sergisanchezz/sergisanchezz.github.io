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

Event cameras are bio-inspired sensors that detect logarithmic changes in pixel-level illumination, generating events asynchronously with microsecond resolution. This principle provides significant advantages over conventional cameras such as high dynamic range, low latency, and low power consumption, making them ideal for dynamic scenarios and challenging lighting conditions.

This work addresses the egomotion estimation of an event camera using a geometric model-based approach and optimization techniques, avoiding the use of learning methods to make it applicable in resource-constrained environments and to deeply understand the problem. A detailed study of the underlying mathematical foundations guides the development of the proposed method. The proposed methodology consists of three main blocks: normal flow estimation, inverse depth estimation, and a robust linear solver. The normal flow estimation method is based on fitting local planes on surfaces of active events, while inverse depth is tackled using optimization techniques to align events at a reference timestamp. Finally, a robust linear solver based on the iterative RANSAC method is implemented, using the inverse depth and normal flow estimates to obtain the camera’s linear velocity.

The method’s performance is evaluated through experiments with synthetic and real data. With synthetic data, the inverse depth optimization algorithm effectively aligns events and converges rapidly to its ground truth value. Additionally, the normal flow estimation recovers both its orientation and magnitude in these examples. Despite certain limitations in synthetic data, this allows the linear solver to obtain the linear velocity.
However, poorly conditioned normal flows are observed when tested with real data. To correct these normal flows, a multi-spatial scale maxpooling method is implemented, which improves estimated orientations but fails to recover magnitude. Conversely, the inverse depth estimation algorithm proves highly effective with real data, correctly aligning events in few iterations. Finally, limitations observed are discussed, and alternatives
for future research are proposed.