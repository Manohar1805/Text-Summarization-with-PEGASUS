# Text-Summarization-with-PEGASUS
This project trains a PEGASUS model for dialogue summarization using the SAMSum dataset. It involves data preprocessing, model training with the Trainer class, and evaluation with ROUGE metrics. The trained model and tokenizer are saved, and the model's performance is demonstrated with sample summaries
Here’s a detailed description of the text summarization project:

---

### Key Components

1. **Model Selection and Setup**
   - **Model**: PEGASUS (Pretrained Encoder-Decoder for Abstractive Summarization) is chosen for its state-of-the-art performance in summarization tasks. 
   - **Tokenizer**: The tokenizer associated with PEGASUS is used to convert text into a format that the model can process.

2. **Data Preparation**
   - **Dataset**: The SAMSum dataset is used, which includes dialogues and their corresponding summaries.
   - **Processing**: The dataset is processed to convert dialogues and summaries into tokenized features compatible with the PEGASUS model. This involves truncating and padding sequences to ensure they fit the model's input size constraints.

3. **Training**
   - **Data Collation**: The `DataCollatorForSeq2Seq` class is used to handle dynamic padding and batching of sequences during training.
   - **TrainingArguments**: Configures various parameters for training, such as batch size, number of epochs, and learning rate.
   - **Trainer**: The `Trainer` class from the `transformers` library is used to manage the training process, including model evaluation and checkpoint saving.

4. **Evaluation**
   - **ROUGE Metric**: The ROUGE (Recall-Oriented Understudy for Gisting Evaluation) metric is employed to evaluate the quality of generated summaries by comparing them to reference summaries.
   - **Metric Calculation**: The `calculate_metric_on_test_ds` function generates summaries for a test set and computes ROUGE scores to assess the performance of the summarization model.

5. **Prediction**
   - **Pipeline**: The `pipeline` function is used to create a summarization pipeline that simplifies the process of generating summaries from new dialogues.
   - **Inference**: The trained model is used to generate summaries for sample dialogues from the test dataset. The generated summaries are compared with reference summaries to evaluate the model's effectiveness.

6. **Model and Tokenizer Saving**
   - **Saving**: The trained model and tokenizer are saved to disk for future use or deployment.

### Summary

This project demonstrates the end-to-end process of training a text summarization model using PEGASUS. It covers data preparation, model training, evaluation, and inference. By leveraging the SAMSum dataset and the PEGASUS architecture, the project aims to produce a high-quality summarization model capable of generating coherent and concise summaries from dialogue data. The evaluation process ensures that the model's performance is quantified using standard metrics, providing insights into its effectiveness in summarizing complex dialogues.

---
