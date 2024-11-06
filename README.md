# Spell Checker Evaluation

## Project Overview
This project evaluates the performance of two spell-checking models: **BERT-based Spell Checker** and **T5-based Spell Checker**. The goal is to assess their effectiveness in correcting spelling errors using metrics such as **Accuracy** and **Mean Reciprocal Rank (MRR)**. This evaluation provides insights into the strengths and weaknesses of each model and discusses potential improvements.

## Dataset

### Source
The dataset used in this evaluation consists of misspelled words along with their correct versions. This data includes a mix of real-world and synthetic spelling errors, designed to simulate typical user inputs and provide a realistic test for the spell-checking models.

### Format
The dataset is structured as follows:
- **Misspelled Word**: The incorrect version of a word, used as the input for the models.
- **Correct Word**: The correct version of the misspelled word, used as the ground truth for evaluation.

### Preprocessing
The dataset was preprocessed to ensure compatibility with the models, including tokenization as required by BERT and T5. Any missing or invalid data entries (e.g., NaN values) were handled to avoid issues during model evaluation.

## Tools and Libraries Used

1. **Transformers (Hugging Face)**: Used to load and evaluate pre-trained language models such as BERT and T5 for spelling correction.
2. **PyTorch**: The backend framework used by the `transformers` library to handle model operations and computations.

### Installation
The following packages are required to run the notebook:
- `transformers`: for loading and utilizing BERT and T5 models.
- `torch`: for running the models.

To install these dependencies, run the following commands:
```bash
pip install transformers
pip install torch
```

## Metrics

Two primary evaluation metrics were chosen to assess the models' performance:

- **Accuracy**: Measures the proportion of times the top suggestion provided by the model matches the correct spelling. This metric gives a straightforward assessment of the model's precision in producing the correct answer as the first suggestion.

- **Mean Reciprocal Rank (MRR)**: Calculates the average of the reciprocal ranks of the first correct suggestion across all test samples. MRR is particularly useful when the model outputs multiple suggestions, as it rewards models that place the correct answer higher on the list.

## Instructions to Run and Reproduce Results

### Set Up the Environment

- Ensure all required libraries are installed. See the **Installation** section above for guidance.
- Download and organize the dataset, ensuring it is accessible within the notebook directory.

### Open the Jupyter Notebook

- Open the `word_correction_assistance.ipynb` notebook in Jupyter.

### Execute the Notebook

- Step through each cell in the notebook sequentially.
- The notebook is structured in sections to load data, preprocess it, load models, make predictions, and evaluate the results.

### Evaluate Models

- The notebook provides functions for calculating Accuracy and MRR. After making predictions with each model, run the evaluation functions to obtain the performance metrics.

### View Results

- After execution, the final cells display the accuracy and MRR for both BERT and T5 models. These results provide a comparison of the models' performance on the spell-checking task.

## Notes

- **Customization**: You may modify the notebook to use different datasets or add other models for further evaluation.
- **Future Improvements**: Consider exploring context-based re-ranking, ensembling, or fine-tuning to improve results if you wish to experiment further.
