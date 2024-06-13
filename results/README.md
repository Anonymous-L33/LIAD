# `results` Folder Contents Description

This `results` directory contains the output from the architecture recovery process applied to the `Teastore` project. Below are descriptions for each of the subdirectories:

## `20240613_13-02-46_teastore`

This folder contains the specific results from the architecture recovery of the `Teastore` project. It includes:

- `metrics_our_to_GT.json`: Evaluation metrics such as MojoFM, A2A, and ARI, reflecting the comparison between recovered architecture of GIARand the ground truth.
- `comparing_with_gt_project.png`: Visual comparison between the recovered architecture and the ground truth architecture, highlighting the similarities and discrepancies.
- **`cluster_result.json`**: Detailed architecture recovery results in JSON format, showing identified modules. Each module is accompanied by a detailed description of its functionality, providing a clear understanding of the project's structure. This file focuses on the basic structure of the identified modules and does not include GPT-based analysis for interpretable dependencies between modules.

## `example`

This folder showcases the output of the complete GIAR process, featuring the interpretable recovered architecture of the `Teastore` project:

- **`recovered_teastore_architecture.png`**: This image provides a comprehensive view of the `Teastore` project’s architecture, including both the interpretable modules and their dependencies. It offers a detailed visualization of the project's architecture.

This example serves as a practical demonstration of applying GIAR with integrated GPT analysis, delivering a thorough architectural overview with interpretable modules and dependencies of a software project.