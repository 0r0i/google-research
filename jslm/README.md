# Adaptive Language Models in JavaScript

This directory contains collection of simple adaptive language models that are
cheap enough memory- and processor-wise to train in a browser on the fly.

## Language Models

### Prediction by Partial Matching (PPM)

Prediction by Partial Matching (PPM) character [language model](ppm_language_model.js).

#### Bibliography

1.  Cleary, John G. and Witten, Ian H. (1984): [“Data Compression Using Adaptive Coding and Partial String Matching”](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.14.4305), IEEE Transactions on Communications, vol. 32, no. 4, pp. 396&#x2013;402.
2.  Ward, David J. and Blackwell, Alan F. and MacKay, David J. C. (2000): [“Dasher -- A Data Entry Interface Using Continuous Gestures and Language Models”](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.36.3318&rep=rep1&type=pdf), UIST '00 Proceedings of the 13th annual ACM symposium on User interface software and technology, pp. 129&#x2013;137, November, San Diego, USA.
3.  Jin Hu Huang and David Powers (2004): [“Adaptive Compression-based Approach for Chinese Pinyin Input”](https://www.aclweb.org/anthology/W04-1104.pdf), Proceedings of the Third SIGHAN Workshop on Chinese Language Processing, pp. 24--27, Barcelona, Spain. ACL.
4.  Cowans, Phil (2005): [“Language Modelling In Dasher &#x2013; A Tutorial”](http://www.inference.org.uk/pjc51/talks/05-dasher-lm.pdf), June, Inference Lab, Cambridge University (presentation).

## Example

Please see a simple example usage of the model API in [example.js](example.js).

## Test Utility

A simple test driver [language_model_driver.js](language_model_driver.js) can be
used to check that the model behaves using [NodeJS](https://nodejs.org/en/). The
driver takes three parameters: the maximum order for the language model, the
training file and the test file in text format.

Example:

```shell
> node --max-old-space-size=4096 language_model_driver.js 7 training.txt test.txt
Initializing vocabulary from training.txt ...
Created vocabulary with 212 symbols.
Constructing 7-gram LM ...
Created trie with 21502513 nodes.
Running over test.txt ...
Results: numSymbols = 69302, ppl = 6.047012997396163, entropy = 2.5962226799087356 bits/char, OOVs = 0 (0%).
```
