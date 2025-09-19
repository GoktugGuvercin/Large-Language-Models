# Large-Language-Models

|  Year   | Model       | Organization      | Approach                                   | Parameters                      | Hugging Face ID |
|:-------:|:-----------:|:-----------------:|:--------------------------------------------:|:-------------------------------:|:---------------:|
|  2017   | Transformer | Google            | Encoder - Decoder (Seq2Seq)                  |                                 |                 |
|  2018   | BERT        | Google            | Encoder Only (MLM, NSP)                      | Base (110M), Large (340M)       | google-bert/bert-base-uncased|
|  2018   | GPT-1       | OpenAI            | Decoder Only (Autoregressive - CLM)          | 117M                            | openai-community/openai-gpt|
|  2019   | Distil BERT | HuggingFace       | Encoder Only (MLM, Distillation)             | 66M                             | distilbert/distilbert-base-cased|
|2019-2020| ALBERT      | Google and Toyota | Encoder Only (MLM, SOP, Parameter Reduction) | Base (12M), XXLarge (235M)      | albert/albert-base-v1 | 


***Encoder Only Models:*** They aim to understand the language, its semantics lying behind it, and create its representation. (Language Representation)
***Decoder Only Models:**** They aim to predict the next word and generate the language. (Language Generation)

### Next Sentence Prediction (NSP)
It is a binary classification task that can be used for pre-training stages; it does not need human annotation. For each sample, a pair of two sentences `A` and `B` is constructed; these two sentences are either chosen from different documents or they follow each other consecutively in a way that `B` is the next sentence of `A`.  

Understanding the relationship between two sentences plays a pivotal role for question answering (QA), natural language inference (NLI) and many other downstream NLP tasks; at this point masked language modeling is unable to capture the mutual correlation of sentences. With this motivation, BERT is not only pre-trained with masked language modeling, but also with next sentence prediction task over classification token. In that way, it would go through a pre-training stage with two different objectives in self-supervised fashion. 


### Sentence Order Prediction (SOP)
Sentence Order Prediction is also a binary classification task, applicable for pre-training stages. As in next sentence prediction, each sample is a pair of two consecutive samples, and multiple samples are constructed. Nevertheless, the order of sentences are swapped in half of the pairs to derive negative examples.  

In ALBERT paper, a self-supervised loss is proposed for sentence-order prediction. With the help of this, inter-sentence coherence aims to be modeled. It is also specifically asserted that this approach is superior to next sentence prediction; the models trained with SOP can achieve a high score for NSP, but the opposite is not possible. 




