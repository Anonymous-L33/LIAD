# GIAR Tool and Dataset

## Introduction

This repository contains the LIAD (LLM-Integrated Architectural Drift Detection) tool and associated datasets for detecting architectural drift between outdated documentation and code. The dataset includes 5 different projects, each equipped with ground truth architecture, architecture document, and module information extracted using Large Language models (GPT/Llama).

## Projects Included

This dataset consists of source code from the following versions of projects, each containing ground truth (`project_gt.json`), architecture documents (`document.txt`) and GPT-extracted module information files (`project_incompleteModules.txt` and `project_completeModules.txt`):

- **MediaStore** - [View Version](https://github.com/ArDoCo/MediaStore3/commit/94c398fa02b3d6b8d71517522a7206d37ed3a9af)
- **TeaStore** - [View Version](https://github.com/ArDoCo/TeaStore/commit/bdc49020a55cfa97eaabbb25744fefbc2697defa)
- **TEAMMATES** - [View Version](https://github.com/ArDoCo/teammates/commit/b24519a2af9e17b2bc9c025e87e4cf60009c425d)
- **BigBlueButton** - [View Version](https://github.com/ArDoCo/bigbluebutton/commit/8fa2507d6c3865a9850004fd6fefd09738e68406)
- **JabRef** - [View Version](https://github.com/ArDoCo/jabref/commit/6269698cae437610ec79c38e6dd611eef7e88afe)

## Usage

To use the GIAR tool to generate interpretable architecture recovery results, please follow these steps:

1. **Download the Tool**: Download this GitHub repository to your local machine.

2. **Run the Tool**: Open a terminal, navigate to the directory containing `run_GIAR`, and execute the following command:

   ```bash
   ./run_GIAR /path/to/project -s /path/to/stopwords.txt -g /path/to/project_ground_truth.json -m /path/to/project_extractedModules.txt
   ```

   - **`/path/to/project`**: Path to the project directory to analyze.
   - **`-s /path/to/stopwords.txt`**: Path to the stopwords file to use during analysis, provided by `ext_tools/stopwords.txt`.
   - **`-g /path/to/project_ground_truth.json`**: Path to the ground truth JSON file for validation.
   - **`-m /path/to/project_extractedModules.txt`**: Path to the file containing module information extracted by Large Language model (GPT/Llama).

   Replace the paths with the actual file paths to your project data.

### Example Command

```bash
./run_LIAD dataset/teammates/teammates -s stopwords/stopwords.txt -g dataset/teammates/teammates_gt.json -m dataset/teammates/teammates_gpt4o_mean.txt
```

## Output Results

After running the tool, a `results` and a a `csv_result` folder will be generated containing the following:

- **Metrics**: Evaluation metrics for architecture recovery like MojoFM, A2A, and ARI are provided in `results/metrics_our_to_GT.json`.
- **JSON Results**: Detailed architecture recovery result in JSON format is provided in `results/cluster_result.json`.
- **Evaluation Summary**: Evaluation metrics summary from multiple runs of architecture recovery and architecture drift detection in different drift degrees, metrics summary for architecture recovery is provided in `csv_result/{project}_combination_recovery_results.csv`, metrics summary for architectural drift is provided in `csv_result/{project}_combination_inconsistency_results.csv`.

## Compatibility

Currently, the `run_LIAD` executable is only compatible with Unix-based operating systems, such as macOS and Linux. We are actively working to provide versions for Windows and other operating systems.

## Disclaimer

Please note that this repository does not include the steps for generating module information based on architecture documents using GPT, nor the steps for generating interpretable module dependencies. This is because the GPT API is not free, and thus integrating it directly into the repository would involve costs. This repository focuses only on the application of the GIAR tool using pre-existing data to recover architecture with interpretable modules.

## Contribution

Feel free to submit pull requests or open issues to suggest improvements or discuss potential changes.