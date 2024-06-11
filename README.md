# GIAR Tool and Dataset

## Introduction

This repository contains the GIAR (GPT-Integrated Interpretable Architecture Recovery) tool and associated datasets for generating interpretable software architecture recovery results. The dataset includes 5 different projects, each equipped with ground truth architecture, architecture document, and module information extracted using GPT.

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
   ./run_GIAR /path/to/project -s /path/to/stopwords.txt -g /path/to/project_ground_truth.json -m /path/to/project_incompleteModules.txt
   ```

   - **`/path/to/project`**: Path to the project directory to analyze.
   - **`-s /path/to/stopwords.txt`**: Path to the stopwords file to use during analysis, provided by `ext_tools/stopwords.txt`.
   - **`-g /path/to/project_ground_truth.json`**: Path to the ground truth JSON file for validation.
   - **`-m /path/to/project_incompleteModules.txt`**: Path to the file containing module information extracted by GPT.

   Replace the paths with the actual file paths to your project data.

### Example Command

```bash
./run_GIAR dataset/mediastore -s ./ext_tools/stopwords.txt -g dataset/mediastore/mediastore_gt.json -m dataset/mediastore/mediastore_incompleteModules.txt
```

## Output Results

After running the tool, a `results` folder will be generated containing the following:

- **Metrics**: Evaluation metrics like MojoFM, A2A, and ARI are provided in `metrics_our_to_GT.json`.
- **Comparison Visualization**: Visual comparison between the recovered architecture and the ground truth is provided in `comparing_with_gt_project.png` .
- **JSON Results**: Detailed architecture recovery result in JSON format is provided in `cluster_result.json`.

## Compatibility

Currently, the `run_GIAR` executable is only compatible with Unix-based operating systems, such as macOS and Linux. We are actively working to provide versions for Windows and other operating systems.

## Disclaimer

Please note that this repository does not include the steps for generating module information based on architecture documents using GPT, nor the steps for generating interpretable module dependencies. This is because the GPT API is not free, and thus integrating it directly into the repository would involve costs. This repository focuses only on the application of the GIAR tool using pre-existing data to recover architecture with interpretable modules.

## Contribution

Feel free to submit pull requests or open issues to suggest improvements or discuss potential changes.