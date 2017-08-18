# LSTM RNN for text generation with Keras
---

- Data processing:
	- convert the characters into integers by mapping unique characters to integers
	- here we will split the book text up into subsequences with a fixed length of 100 characters, an arbitrary length 
	- further we can just as easily split the data up by sentences and pad the shorter sequences and truncate the longer ones
	- slide the window of 100 around the whole book allowing each character a chance to be learned
	- to feed into  keras convert the output patterns into one-hod encoding 
---
- Defining LSTM:
	- single hiddent LSTM layer with 256 memory units
	- using dropout at 20
	- output layer is dense layer using softmax activation
	- we are modeling the training dataset to learn the probability of each chracter in dataset
	- there is no testing dataset
	- network is slow to train, so we would use checkpoints to record all network weights to a file each time an improvement is observed
---
- Generating text with LSTM network:
	- we load data from a checkpoint
	- start off with a seed sequence as input 
	- generate the next characters
	- then update the seed sequence to add the generated characters and trim off the first character
	 
