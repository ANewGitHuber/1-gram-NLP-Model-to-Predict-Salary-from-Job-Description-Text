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

#### Great prediction samples for predicting high salary

[1] "Sales Executive Channel Manager IP/Ethernet Networking COMPANY PROFILE Our client is a world class leader in delivering IP/Ethernet network solutions Internationally. In Europe they have **** distribution partners supporting over **** VARs, Resellers and SIs and also OEM partners. They create IP networks that seamlessly connect voice, data and video services. Enterprise customers can build complete endtoend networking solutions through a single vendor, with coretoedge technologies ranging from powerful **** Gigabit Layer **** switches right through to media converters. Service Providers use our wide range of access, aggregation and backbone solutions. The products range from industry leading media gateways which allow voice, video and data services to be delivered to the home and business, right through to highend chassisbased platforms providing significant network infrastructure. INDUSTRY KNOWLEDGE Wide Area Network (WAN) connectivity. Core Network Solutions LAN Security Fiber Connectivity IP Video Surveillance IP Triple Play Voice over IP Broadband Access Ethernet Transport IPv**** **** Gigabit Wireless THE ROLE The challenge now is to increase the existing success stories into well published and compelling solutions for the mid to large market. Driving structure into the current channel and developing new and effective routes to market to accelerate growth. A key part of..." (Prediction 73727.86 / Normalized 80000)

[2] "General Derivatives Lawyer Our client is one of the world's leading investment banks. Their worldrenowned legal division provides comprehensive legal support to all areas of the investment bank and has lawyers based across the globe. The crossderivatives group provides strategic and transactional legal coverage to the firm's derivatives and trading businesses in London. The legal department's coverage model allows the firm's lawyers to specialise whilst maintaining diversity of practice and the flexibility to develop new areas of expertise, thereby meeting changing business needs and enhancing the lawyer's own career development. Currently, the derivatives legal team seeks a crossderivatives lawyer with a sound instinct for risk management, who knows when to escalate, can integrate with other core risk functions, and articulates the firm's governance and risk policies. Typically a lawyer will be assigned up to three distinct areas within the crossderivatives group at any time. These are expected to change periodically. The main function of the role is to be a cross product derivatives lawyer in the derivatives legal team covering a range of different asset classes (which may include credit and equity derivatives, fixed income rates and FX). The lawyer will provide legal support to the respective trading and structuring..." (Prediction 69269.06 / Normalized 80000)

### Bad prediction samples for predicting high salary

[1] "Huge scope to make a positive impact on a highprofile business Stimulating and challenging leadership role Oversee the integration of major projects Fastpaced and challenging environment Network Rail is at the heart of revitalising Britain s railway. From the rejuvenation of King s Cross station and the upgrade and expansion of Thameslink, to Europe s largest civil engineering project Crossrail we're involved in some of the most ambitious and diverse ventures that this country has ever seen. The work we re doing is vital for the nation s economic prosperity, transforming how people travel. Join us in this key role and you ll play an important part in ensuring our success. Developing and managing a cohesive national plan, you ll be the powerhouse driving integration of the varied major projects and resolving conflicts between regions and programmes. Ours is a business that s constantly evolving, so you ll also forecast the needs of tomorrow and take responsibility for successful integration of future corporate requirements. You ll need: Membership of a relevant professional body with chartered status Impressive track record of management of significant projects in the construction and/or rail industries Proven ability to think strategically and tactically Strong commercial focus..."

[2] "This is a very high growth business, driven by technical innovation and service excellence, which is setting new standards in its industry. The board are seeking to appoint their first Sales Director, in what will be an exciting and rewarding new role. THE COMPANY: Awardwinning service and product business that spans the IT and travel sectors Change oriented and agile, moves at a fast pace and keeps ahead of the competition Keen to more formally develop sales strategy in line with ambitious plans for the future Focussing on developing the people and processes for a larger, complex business THE JOB: New role as the company s first Sales Director, reporting to the Managing Director Total responsibility for building, developing and focussing the sales force to win new business across a wide range of customers in size and industry sector Ensures that the sales force have the training, support infrastructure and marketing tools to deliver exceptional results and manages them to be highly effective, both individually and as a team Helps the board to develop sales strategy and advises on organisation structures Builds relationships with large customer accounts to maximise profitable revenue THE PERSON: At Sales Director level already Strong sales..."


