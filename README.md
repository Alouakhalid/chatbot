🧠 Simple NLTK Chatbot
This is a basic rule-based chatbot built using Python and the NLTK (Natural Language Toolkit) library. The chatbot can respond to simple greetings and farewell messages.

🚀 Features
Responds to greetings like "hello"

Answers "how are you?" with predefined responses

Gracefully exits when user types "bye"

Returns a default message for unrecognized input

Utilizes NLTK's punkt tokenizer for potential future expansion

🛠 Requirements
Python 3.x

NLTK

You can install the required library using pip:

bash
Copy
Edit
pip install nltk
🧰 How It Works
Preprocessing: Input is converted to lowercase.

Response Matching: It checks if a known keyword is in the user's input and responds accordingly.

Fallback: If no keyword is found, a default response is used.

💻 Usage
Clone or download this repository.

Run the script using:

bash
Copy
Edit
python chatbot.py
Chat away! Type something like:

text
Copy
Edit
You: hello
Chatbot: Hey! How can I help you?

You: how are you?
Chatbot: I'm here to help!

You: bye
Chatbot: Take care!
🧠 Example Code
python
Copy
Edit
import nltk
import random

nltk.download('punkt')

responses = {
    "hello": ["Hi there!", "Hello!", "Hey! How can I help you?"],
    "how are you": ["I'm good, thanks!", "Doing well! What about you?", "I'm here to help!"],
    "bye": ["Goodbye!", "See you later!", "Take care!"],
    "default": ["Sorry, I didn't understand that.", "Can you rephrase that?", "I'm not sure how to respond."]
}

def preprocess(text):
    return text.lower()

def get_response(user_input):
    user_input = preprocess(user_input)
    for key in responses:
        if key in user_input:
            return random.choice(responses[key])
    return random.choice(responses["default"])

def chat():
    print("Chatbot: Hello! Type 'bye' to exit.")
    while True:
        user_input = input("You: ")
        if "bye" in user_input.lower():
            print("Chatbot:", random.choice(responses["bye"]))
            break
        print("Chatbot:", get_response(user_input))

if __name__ == "__main__":
    chat()
📝 Notes
This is a simple demo meant for educational purposes.

The keyword-based approach can be improved by integrating NLP techniques or machine learning models for more intelligent responses.

