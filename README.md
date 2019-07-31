# Overview
This is a repository to publish Dependency-based Japanese Word Embeddings which we trained for experiments in the article "係り受けに基づく日本語単語埋込 (Dependency-based Japanese Word Embeddings)" ( Article URL https://ai-lab.lapras.com/nlp/japanese-word-embedding/).

We applied the method proposed in the paper "Dependency-based Word Embeddings" to Japanese.  
To prepare the training data, we first extracted sentences from Japanese Wikipedia dumps.  
Then, we parsed them using an NLP framework "GiNZA".  
Finally, we trained the embeddings with the script by the first author of the paper.  

# Parameter Settings
The parameter settings for the experiments is as below where DIM is the number of dimensions written in each file name.
```
-size DIM -negative 15 -threads 20
```

# Download URL
You can download the data from the URL below.
The structure of the files in the bucket is as follows:
- README.me
  - A Readme file
- dep-ja-100dim
  - 100 dimensional word vectors
- dep-ja-200dim
  - 200 dimensional word vectors
- dep-ja-300dim
  - 300 dimensional word vectors

# When using the data for your research
When writing your paper using this data, please cite the following bibtex,


    @misc{matsuno2019dependencybasedwordembeddings,  
        title  = {Dependency-based Word Embeddings},  
        author = {Tomoki, Matsuno},  
        url    = {https://github.com/lapras-inc/dependency-based-japanese-word-embeddings},  
        year   = {2019}  
    }  
