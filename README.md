 Cancer Mutation Classification Using Deep Learning
This project predicts the cancer class (1–9) based on three inputs:

DNA mutation text

Gene name

Variation

It uses a pretrained deep learning model (cancer_model.h5) trained on the MSK-IMPACT dataset provided in the MSK Challenge on Kaggle.

 Files & Folders
File / Folder	Description
cancer_model.h5	Trained deep learning model
training_variants	CSV with gene, variation, and class
training_text	TXT with ID and mutation text
predict.py	Python script to predict cancer class
README.md	Project overview and instructions

 Installation
Make sure you have the following Python packages installed:

bash
Copy
Edit
pip install tensorflow pandas numpy scikit-learn
 How to Run
bash
Copy
Edit
python predict.py
This will load the model and tokenizer and run an example prediction:

python
Copy
Edit
dna_text = "This mutation affects the kinase domain of the EGFR gene."
gene = "EGFR"
variation = "L858R"
 Output:

vbnet
Copy
Edit
Predicted Cancer Class: 2
 Using Custom Input
You can modify the predict_cancer_class() function call in predict.py to use your own mutation text, gene name, and variation:

python
Copy
Edit
predict_cancer_class("sample mutation description", "GENE_NAME", "VARIATION")
 Model Input Explanation
Input	Type	Description
Text	String	Mutation description
Gene	Categorical	Encoded using LabelEncoder
Variation	Categorical	Encoded using LabelEncoder

The text is tokenized using Keras Tokenizer and padded to max length 500.

 Output
The model outputs a class label from 1 to 9 indicating the predicted cancer class for the mutation.

 Notes
If the input gene or variation was not in the training dataset, the model will return an "Unknown" warning.

This is a multiclass classification task.
