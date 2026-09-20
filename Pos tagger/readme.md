pos tagger noun ki verb ye karta determnin

import spacy

nlp = spacy.load("en_core_web_sm")

doc = nlp("Keshav is studying machine learning.")

for token in doc:
    print(token.text, token.pos_, token.tag_)
