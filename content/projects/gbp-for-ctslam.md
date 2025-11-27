---
title: "Gaussian Belief Propagation for Continuous-Time SLAM"
start_date: "2025-02-01"
end_date: "2025-07-01"
affiliations:
  - name: "ETH Zürich (Vision for Robotics Lab)"
    url: "https://v4rl.ethz.ch/"
authors: ["Sergi Sánchez Orvay"]
supervisors: ["Xinyi Li", "William Talbot", "Dr. David Hug", "Dr. Cornelius von Einem", "Prof. Dr. Margarita Chli"]
github_link: "https://github.com/VIS4ROB-lab/hyperion" # Add link here if available
report_link: "/files/gbp_for_ctslam.pdf" # Link to the uploaded file
draft: false
layout: "project_single"
---

Continuous-Time SLAM (CTSLAM) has emerged as a compelling alternative to conventional discrete-time approaches, representing the robot trajectory as a smooth function over time rather than a sequence of fixed-interval poses. This continuous formulation naturally fuses asynchronous, multi-rate sensors without explicit interpolation or aggregation, preserves full measurement fidelity, and yields more consistent estimates. However, CTSLAM often incurs higher computational cost.

Gaussian Belief Propagation (GBP) offers a distributed inference framework on factor graphs, in which variables and measurements exchange Gaussian messages to perform local, incremental updates. Unlike centralized Non-Linear Least Squares (NLLS) solvers (e.g. Ceres), GBP can exploit parallelism, detect converged nodes, and avoid repeated global relinearization, making it well suited for real-time, largescale, or collaborative SLAM applications.

Hyperion—the first open-source continuous-time GBP solver—demonstrated significant speedups over existing spline implementations, yet exhibited numerical instabilities in visual SLAM scenarios. These failures hinder its deployment as a reliable system. In this work, the root causes of divergence—poorly conditioned landmark covariances and underconstrained spline tails—are systematically analysed and introduce different regularization strategies within an online CTSLAM pipeline: diagonal relaxation of precision matrices, Levenberg–Marquardt damping in node updates, message damping, and tail-fixing of spline control points. These techniques are evaluated in both a controlled simple problem and a realistic indoor sequence under varying noise, and outlier conditions. Regularized Hyperion is further benchmarked against a Ceres-based solver in full history and sliding window modes.

Results show that the combined regularization scheme yields stable convergence, high accuracy, and robustness to outliers, while Hyperion consistently outperforms Ceres in runtime—demonstrating its potential as a deployable continuous-time SLAM solution.