# GIAR Tool and Dataset

## Introduction

This repository contains the GIAR (GPT-Integrated Interpretable Architecture Recovery) tool and associated datasets for generating interpretable software architecture recovery results. The dataset includes 5 different projects, each equipped with ground truth architecture, architecture document, and module information extracted using GPT.

## Disclaimer

This repository does not provide the steps involving GPT for generating module information based on architecture documents nor the steps for generating interpretable module dependencies. It focuses only on the application of the GIAR tool using pre-existing data.

## Projects Included

This dataset consists of source code from the following versions of projects, each containing ground truth (`project_gt.json`), architecture documents (`document.txt`) and GPT-extracted module information files (`project_notaccurateModules.txt` and project_accurateModules.txt`):

- **MediaStore** - [View Version](https://github.com/ArDoCo/MediaStore3/commit/94c398fa02b3d6b8d71517522a7206d37ed3a9af)
- **TeaStore** - [View Version](https://github.com/ArDoCo/TeaStore/commit/bdc49020a55cfa97eaabbb25744fefbc2697defa)
- **TEAMMATES** - [View Version](https://github.com/ArDoCo/teammates/commit/b24519a2af9e17b2bc9c025e87e4cf60009c425d)
- **BigBlueButton** - [View Version](https://github.com/ArDoCo/bigbluebutton/commit/8fa2507d6c3865a9850004fd6fefd09738e68406)
- **JabRef** - [View Version](https://github.com/ArDoCo/jabref/commit/6269698cae437610ec79c38e6dd611eef7e88afe)

## Usage

To use the GIAR tool to generate interpretable architecture recovery results, please follow these steps:

1. **Download the Tool**: Download the `run_GIAR` executable from this GitHub repository to your local machine.

2. **Run the Tool**: Open a terminal, navigate to the directory containing `run_GIAR`, and execute the following command:

   ```bash
   ./run_GIAR /path/to/project -s /path/to/stopwords.txt -g /path/to/ground_truth.json -m /path/to/mediastore_notaccurateModules.txt
   ```

   - **`/path/to/project`**: Path to the project directory to analyze.
   - **`-s /path/to/stopwords.txt`**: Path to the stopwords file to use during analysis, provided by `ext_tools/stopwords.txt`.
   - **`-g /path/to/ground_truth.json`**: Path to the ground truth JSON file for validation.
   - **`-m /path/to/mediastore_notaccurateModules.txt`**: Path to the file containing module information extracted by GPT.

   Replace the paths with the actual file paths to your project data.

### Example Command

```bash
./run_GIAR dataset/mediastore -s ./ext_tools/stopwords.txt -g dataset/mediastore/mediastore_gt.json -m dataset/mediastore/mediastore_notaccurateModules.txt
```

## Contribution

Feel free to submit pull requests or open issues to suggest improvements or discuss potential changes.