import spacy

# Load spaCy NLP model
nlp = spacy.load("en_core_web_sm")

# Define a function to pre-process text data
def preprocess_text(text):
    # Remove punctuation and special characters
    text = text.strip().lower().translate(str.maketrans("", "", string.punctuation))
    # Tokenize the text into words or phrases
    doc = nlp(text)
    tokens = [token.text for token in doc]
    # Lemmatize the tokens to reduce dimensionality of the data
    lemmas = [token.lemma_ for token in doc]
    return lemmas

# Pre-process sample text
text = "Telugu is a Dravidian language spoken by about 85 million people in India."
lemmas = preprocess_text(text)
print(lemmas)
 
