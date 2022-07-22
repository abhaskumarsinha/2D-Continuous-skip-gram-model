# 2D-Continuousskip-gramm-model
A word2vec embedding, called Continuous Skip Gram Model encodes each word to a Vector depending on how closely they are related or how often they are used along.

## Dataset

We are using Asimov's - The Last Question (Nov 1956) as our dataset for Word2Vec Embedding.

## Abstract

There are multiple ways to convert lines/words of Natural Language to Vectors to feed them to pipelines to process data. Two sorts of popular ways, we know - Continuous Skip Gram Model and Continuous Bag of Words. Continuous Bag of Words is known to perform very well with large datasets involving tasks like hashing, searching, and Machine Comprehension, while we use Continuous Skip Gram Model which is known to perform very well with short stories. The mechanism of Continuous Skip Gram Model is exactly the opposite of CBOW. Here's a small notebook demonstrating the very simple case of Skip Gram Model with variable window size and dataset of only one target word and one context word. Since, there are only two words in total, we use *linear* or *sigmoid* activation function in the final layer instead of the original model which used *softmax* because softmax requires **atleast** two output to work. We get a single scalar representation or embedding which is a special case of 1D Vector and we con compare two words, based on similarity based on scalar value distance between the encoding of two numbers. Such representation is not too helpful because we can't often represent non singular dimensional closeness in such cases. The notebook uses `tf.keras.layers.Dot(axes=1)([vec1, vec2])` which has been implemented in TensorFlow 2.0 for merging Context and Target word cases and `tf.keras.layers.Embedding(vocab_size, output_size)` for embedding the words to float numbers between -1 to 1. The notebook can easily be extended to multiple dimensions according to original paper using Dot Layer by Keras. The whole work is based on the original papers [1, 2]. The word2vec models are a good alternative to GloVe models for embedding NLP text words to vectors and sentences to Matrices. They have been successfully been applied to some of the top most state of art Models like - T4 Transformers, BiDAF Machine Comprehension networks or so [3, 4]

## Sample Results

![download](https://user-images.githubusercontent.com/31654395/180498566-86245668-53c8-4383-bef9-c8175876170d.png)

A small plot of some words in 2D Directions demonstrating closeness (positivity in skip gram) or far-ness (negativitiy in skip gram) as generated by our Model.

## Biblography

1. Mikolov, Tomas, et al. "Efficient estimation of word representations in vector space." arXiv preprint arXiv:1301.3781 (2013).
2. Mikolov, Tomas, et al. "Distributed representations of words and phrases and their compositionality." Advances in neural information processing systems 26 (2013).
3. Raffel, Colin, et al. "Exploring the limits of transfer learning with a unified text-to-text transformer." J. Mach. Learn. Res. 21.140 (2020): 1-67.
4. Seo, Minjoon, et al. "Bidirectional attention flow for machine comprehension." arXiv preprint arXiv:1611.01603 (2016).

  
