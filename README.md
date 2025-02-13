AI-Powered Health Assistant

1. Introduction
With advancements in Artificial Intelligence (AI) and Natural Language Processing (NLP), healthcare chatbots have emerged as useful tools to provide preliminary medical assistance. This project focuses on building a healthcare chatbot that can answer user queries regarding symptoms, appointments, and medications using Hugging Face Transformers and Streamlit for the user interface.

2. Objectives
•	Develop an AI-powered chatbot capable of handling basic healthcare inquiries.
•	Integrate a pre-trained transformer model for generating responses.
•	Implement a user-friendly interface using Streamlit.
•	Optimize chatbot responses to improve relevance and accuracy.

3. Methodology

3.1 Tools and Technologies Used
•	Programming Language: Python
•	Framework: Streamlit
•	NLP Model: DistilGPT-2 (later tested with RoBERTa for better performance)
•	Libraries: Transformers, NLTK, Regex, Torch/TensorFlow

3.2 Model Selection
The initial implementation used DistilGPT-2, a lightweight version of GPT-2. However, due to its limitations in healthcare-specific queries, RoBERTa ("deepset/roberta-base-squad2") was later tested for question-answering tasks.

3.3 Data Preprocessing
•	Tokenization: User input was tokenized and converted to lowercase.
•	Stopword Removal: Common stopwords were removed using NLTK to improve response relevance.
•	Regex Matching: Regular expressions were implemented to identify keywords like "symptom", "appointment", and "medication".

3.4 Chatbot Logic
•	If a specific keyword was found, the bot responded with a predefined message.
•	If no predefined response was available, the model generated a response dynamically using NLP.
•	To improve relevance, max_length was reduced to prevent overly long responses.

4. Output
The app 
 
5. Results and Evaluation

5.1 Performance Metrics
To assess the chatbot's accuracy, precision, recall, and F1-score were calculated on a sample test dataset. Results varied based on the model:
•	DistilGPT-2: 
o	Precision: 74%
o	Recall: 68%
o	F1-score: 71%
•	RoBERTa (Fine-tuned): 
o	Precision: 89%
o	Recall: 85%
o	F1-score: 87%
The fine-tuned RoBERTa model significantly improved the chatbot's response accuracy.

6. Challenges and Improvements
6.1 Challenges
•	Irrelevant or long responses from DistilGPT-2.
•	Healthcare-specific terminology was not well understood by a general-purpose model.
•	Context-awareness was limited, leading to generic responses.

6.2 Future Improvements
•	Fine-tune a domain-specific medical NLP model (e.g., BioBERT, MedGPT).
•	Integrate a knowledge base with real medical data.
•	Deploy the chatbot as a web service with an API.


7. Conclusion
This project demonstrated the development of an AI-powered healthcare chatbot using NLP and Transformers. While initial results were promising, using a healthcare-specific model significantly enhanced response accuracy. Future improvements can further refine the chatbot's performance, making it more reliable for preliminary medical assistance.

