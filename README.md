# Overview
This is a repository to share dependency-based japanese word embeddings which we trained for experiments in the article [係り受けに基づく日本語単語埋込 (Dependency-based Japanese Word Embeddings)](https://ai-lab.lapras.com/nlp/japanese-word-embedding/).

We applied the method proposed in the paper [Dependency-based Word Embeddings](https://www.aclweb.org/anthology/P14-2050) to Japanese.  

# Training Details

To prepare the training data, we first extracted sentences from [Japanese Wikipedia dumps](https://dumps.wikimedia.org/jawiki/).  
Then, we parsed them using an NLP framework [GiNZA](https://github.com/megagonlabs/ginza).  
Finally, we trained the embeddings with the script provided in [the page of the paper's first author](https://levyomer.wordpress.com/2014/04/25/dependency-based-word-embeddings/).  

The parameter settings for the experiments is as below where DIM is the number of dimensions written in each file name.
```
-size DIM -negative 15 -threads 20
```

# Download URL
You can download the data from here.
The bucket contains these files:

- Embeddings/
  - dep-ja-100dim
    - 100 dimensional word vectors
  - dep-ja-200dim
    - 200 dimensional word vectors
  - dep-ja-300dim
    - 300 dimensional word vectors

# How to Use the Embeddings
You can use the embeddings in the same way as embeddings trained by using the original implementation of [Word2Vec](https://code.google.com/archive/p/word2vec/).

Here is an example code to load them from your Python script.

```
from gensim.models import KeyedVectors
vectors = KeyedVectors.load_word2vec_format("path/to/embeddings")
```

# When Using Them for Your Research
When writing your paper using them, please cite this bibtex,


    @misc{matsuno2019dependencybasedwordembeddings,  
        title  = {Dependency-based Word Embeddings},  
        author = {Tomoki, Matsuno},  
        affiliation = {LAPRAS inc.},
        url    = {https://github.com/lapras-inc/dependency-based-japanese-word-embeddings},  
        year   = {2019}  
    }  

# References
松田寛, 大村舞, 浅原正幸. 短単位品詞の用法曖昧性解決と依存関係ラベリングの同時学習, 言語処理学会 第 25 回年次大会 発表論文集, 2019.  
Mikolov, T., Chen, K., Corrado, G. & Dean, J. (2013). Efficient estimation of word representations in vector space. arXiv preprint arXiv:1301.3781, .  
Levy, O. & Goldberg, Y. (2014). Dependency-Based Word Embeddings. Proceedings of the 52nd Annual Meeting of the Association for Computational Linguistics (Volume 2: Short Papers) (p./pp. 302--308), June, Baltimore, Maryland: Association for Computational Linguistics.  
