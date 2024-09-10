# Named Entity Recognition and Data Linkage with BERT

## Dataset Description

The dataset used for this project is a named entity recognition (NER) dataset. It contains sentences with words tagged for their part of speech (POS) and named entity labels. The dataset has the following columns:

- `Sentence #`: The sentence number
- `Word`: The word in the sentence
- `POS`: Part of speech tag
- `Tag`: Named entity label

## Steps Performed

1. **Loading the Dataset**
   - Imported the dataset using pandas with Latin-1 encoding.
   - Displayed the first 30 rows to understand the structure.

2. **Handling Missing Values**
   - Filled missing values using forward fill method to ensure each word is associated with a sentence number.

3. **Label Encoding**
   - Encoded the `Sentence #` column to convert sentence identifiers into numerical format.

4. **Renaming Columns**
   - Renamed columns for better readability: `Sentence #` to `sentence_id`, `Word` to `words`, and `Tag` to `labels`.

5. **Converting Labels to Uppercase**
   - Converted all labels to uppercase for consistency.

6. **Splitting the Data**
   - Split the data into training and testing sets with an 80-20 ratio.

7. **Preparing Training and Testing Data**
   - Created separate DataFrames for training and testing data.

8. **Training the Model**
   - Used the `simpletransformers` library to train a BERT model for NER.
   - Defined the unique labels and set training arguments.
   - Trained the model on the training data.

9. **Evaluating the Model**
   - Evaluated the model on the test data to obtain metrics like precision, recall, and F1 score.

10. **Making Predictions**
    - Used the trained model to make predictions on a sample sentence.

## Results

- **Evaluation Metrics**
  - Loss: 0.1712
  - Precision: 82.82%
  - Recall: 76.29%
  - F1 Score: 79.42%

- **Sample Prediction**
  - Input: "What is the old name of Sri Lanka"
  - Output: 
    ```
    [{'What': 'O'},
     {'is': 'O'},
     {'the': 'O'},
     {'old': 'O'},
     {'name': 'O'},
     {'of': 'O'},
     {'Sri': 'B-GEO'},
     {'Lanka': 'B-GPE'}]
    ```

Named entity recognition and data linkage are the same in this context. This README provides a detailed overview of the dataset, the steps performed during the project, and the results obtained from training and evaluating the NER model.
