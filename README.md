## A Unigram NLP Model to Predict Salary from Job Description Text

This project establishes a 1-gram language model to predict salary from job description text. 

### N-gram Language Model

n-grams: An n-gram is a contiguous sequence of n items from a given sample of text or speech. For example, in the sentence "The cat sat on the mat", the 2-grams (bigrams) would be "The cat", "cat sat", "sat on", "on the", "the mat".

Probability Estimation: The probability of each n-gram is calculated based on its frequency in the training corpus. For a unigram model (where n=1), the probability of a word occurring is simply its frequency divided by the total number of words in the corpus.

Smoothing/Laplace Smoothing: Since some n-grams may not appear in the training corpus, smoothing techniques are used to assign them a small, non-zero probability. This prevents the model from assigning a zero probability to unseen words or sequences when predicting the next item in a sequence.

Backoff and Interpolation: These techniques are used to handle cases where higher-order n-grams (with larger n) are not found. The model can "back off" to using lower-order n-grams, or use interpolation to combine probabilities from different orders.

N-gram models have a wide range of applications in NLP, including:
Text Prediction - Used in predictive text input systems, like those on smartphones, to suggest the next word.
Speech Recognition - Helps in determining the sequence of words that best matches a given sequence of sounds.
Machine Translation - Used in statistical machine translation systems to estimate the probability of a sequence of words in the target language.
Spelling Correction - Helps in identifying and correcting misspelt words based on the context.
Information Retrieval - Used to improve search engine results by considering the probability of sequences of words rather than just individual words.

The unigram model is a type of language model based on the assumption that each word (or token) in a document or sentence occurs independently of the others. It is the simplest form of an n-gram model, where "n" refers to the number of words considered as a context. unigram model is an n-gram model where n=1. This model is fast and fairly accurate but ignores the order and context of the text, which can limit the effectiveness of the model. In the code, it is possible to change the ngrams parameter of TMEF-dfm in line 52 to turn the model into a language model with higher n dimensions. n=2 was tried and the runtime increased exponentially with little performance improvement.

### Model Result

Coefficient Distribution

![Coefficient in Model](https://github.com/ANewGitHuber/A-Unigram-NLP-Model-to-Predict-Salary-from-Job-Description-Text/assets/88078123/af444eb0-5401-45a8-ad27-e020b4982dd2)

LASSO MSE

![Lasso MSE](https://github.com/ANewGitHuber/A-Unigram-NLP-Model-to-Predict-Salary-from-Job-Description-Text/assets/88078123/86f87dea-468e-4d17-affd-3a5dbfb49e7b)

Accuracy

![Accuracy](https://github.com/ANewGitHuber/A-Unigram-NLP-Model-to-Predict-Salary-from-Job-Description-Text/assets/88078123/18e213df-0ff4-48da-a05a-c3d4cf145573)

### Interpretation

#### Two great prediction samples for predicting high salary
[1] "Sales Executive Channel Manager IP/Ethernet Networking COMPANY PROFILE Our client is a world class leader in delivering IP/Ethernet network solutions Internationally. In Europe they have **** distribution partners supporting over **** VARs, Resellers and SIs and also OEM partners. They create IP networks that seamlessly connect voice, data and video services. Enterprise customers can build complete endtoend networking solutions through a single vendor, with coretoedge technologies ranging from powerful **** Gigabit Layer **** switches right through to media converters. Service Providers use our wide range of access, aggregation and backbone solutions. The products range from industry leading media gateways which allow voice, video and data services to be delivered to the home and business, right through to highend chassisbased platforms providing significant network infrastructure. INDUSTRY KNOWLEDGE Wide Area Network (WAN) connectivity. Core Network Solutions LAN Security Fiber Connectivity IP Video Surveillance IP Triple Play Voice over IP Broadband Access Ethernet Transport IPv**** **** Gigabit Wireless THE ROLE The challenge now is to increase the existing success stories into well published and compelling solutions for the mid to large market. Driving structure into the current channel and developing new and effective routes to market to accelerate growth. A key part of"...

[2] "General Derivatives Lawyer Our client is one of the world's leading investment banks. Their worldrenowned legal division provides comprehensive legal support to all areas of the investment bank and has lawyers based across the globe. The crossderivatives group provides strategic and transactional legal coverage to the firm's derivatives and trading businesses in London. The legal department's coverage model allows the firm's lawyers to specialise whilst maintaining diversity of practice and the flexibility to develop new areas of expertise, thereby meeting changing business needs and enhancing the lawyer's own career development. Currently, the derivatives legal team seeks a crossderivatives lawyer with a sound instinct for risk management, who knows when to escalate, can integrate with other core risk functions, and articulates the firm's governance and risk policies. Typically a lawyer will be assigned up to three distinct areas within the crossderivatives group at any time. These are expected to change periodically. The main function of the role is to be a cross product derivatives lawyer in the derivatives legal team covering a range of different asset classes (which may include credit and equity derivatives, fixed income rates and FX). The lawyer will provide legal support to the respective trading and structuring"...


