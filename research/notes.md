# Missing background

Background knowledge:
* What is a tokenizer?
	* text to tokens
* What kinds of tokenizers are there?
	* word level, character level, subword level
	* there are different algorithms for deciding the subword level tokenizers
	* wordpiece, byte-pair-encoding (BPE), unigram language model (Unigram), regular expression tokenisation method based on the WordPunct tokenizer of NLTK
* How do tokenizers fit in NLP
	* tokenizers are necessary in any 
* How would existing tokenizers do for a language like NENA?
	* people have looked at arabic [[alkaoud2020arabic.pdf]]
	* 

# Questions
Q: What tokenization methods do I want to try?
	A: at least what is used in Kurdish paper and in Arabic paper

Q: What will the training data be?
	A: glosses (how do we clean?)
	B: glosses manually adjusted
	C: texts (how do we clean?)
	D: all of these but glossed?

Q: How do I want to evaluate this?
	A: look at the tokens and ask if they make sense?

Can you manually define tokenizer?