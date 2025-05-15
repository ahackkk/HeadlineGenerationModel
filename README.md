Kyrgyz Headline Generator This project trains an mT5 model to generate headlines in Kyrgyz from article texts. It uses the Hugging Face transformers library.

Files:
-KyrgyzHeadlineGeneration.ipynb - training and generation code
-kg_dataset.csv - dataset with articles and headlines
-Kyrgyz-Headline-Generation-using-Transformers.pptx — project presentation
-“HeadlineGeneration”ProjectReport.pdf — project report

Setup Clone the repo and install dependencies:
-pip install transformers datasets evaluate rouge_score nltk torch

Put your dataset path in the code (default is dataset.csv).
Usage Run KyrgyzHeadlineGeneration.ipynb to train and evaluate the model. After training, use the saved model in headline_model/ to generate headlines without retraining.
Example for inference:
"from transformers import MT5ForConditionalGeneration, MT5Tokenizer
tokenizer = MT5Tokenizer.from_pretrained("headline_model") model = MT5ForConditionalGeneration.from_pretrained("headline_model")
input_text = "Your article text here" inputs = tokenizer(input_text, return_tensors="pt", truncation=True) outputs = model.generate(**inputs) print(tokenizer.decode(outputs[0], skip_special_tokens=True))"
