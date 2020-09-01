### Summaries of literature survey on "Comparison of 2 Documents"

* Paper Title : [Unstructured document compliance checking](https://www.ijcai.org/proceedings/2020/0613.pdf)
  1. Entity: IBM China
  1. Publication: IJCAI 2020
  1. Solution:
    1. It provides multi-level deep semantic comparison.
      1. Sentence Level -> GNN based syntactic sentence encoder to capture semantic and syntactic clues of sentences.
          1. Dataset: Banking, open domain - SNLI
      1. Clause Level -> Attention based semantic relatedness detection model to find relevant legal clauses.
          1. Dataset: No existing data, so annotated themselves

* Paper Title: [Extent of repetition in Contract language](https://www.aclweb.org/anthology/W19-2203.pdf)
  1. Publication:ACL 2019
  1. Problem: Measure the extent to which contract language in English is repetitive compared with the language of other English language corpora
  1. results:
      1. far fewer rare word types and higher sentence similarity
      1. contracts are focused on creating arrangements between parties, similar to those created before
  1. Dataset: EDGAR and google to extract contracts specific to categories
      1. Types: Prime contracts, Subcontracts, Non disclosure agreements, Purchase orders, Service agreements

* Paper Title: [Legal Document similarity using triples extracted from Unstructured text](http://lrec-conf.org/workshops/lrec2018/W22/pdf/9_W22.pdf)
  1. Problem: Find similar legal documents
  1. Solution:
      1. Created ontology for the selected dataset
      1. extract triples from documents for comparison
      1. similarity score is based on RDF path length from previous paper [ LODIFIER: generates linked data from unstructured text ] 
  1. Cited paper : Lodifier paper link: https://www.slideshare.net/isabelleaugenstein/lodifier-generating-linked-data-from-unstructured-text
  1. Dataset:  Income Tax Act which deals with ‘Changes in constitution, succession, and dissolution of firms and partnerships’. The Sections of the act which were of interest are Section 187, 188, 188A, 189 and 189A

* Paper Title: [Plagiarism– state of the art and evaluation](https://arxiv.org/abs/1603.03014) 
  1. Problem: Survey of methods
  1. Solution: 
      1. Citation -  characterizes a document by its citation sequence, rather than the text itself
	        1. language independant 
	        1. reduces complexity compared to the comparison of full documents
      1. semantic similarity - X sim: similarity values between texts based on the statistical evaluation of word co-occurences
	        1. reduce the amount of documents to compare through a prior title comparison
	        1. compare within same category
      1. Semantic Role labelling - Similarity between sentences
	        1. split sentences and assign their parts to different label groups
	        1. semantic annotation of terms with the help of the semantic lexicon WordNet
      1. Latent Semantic Indexing - probabilistic model for words based on a SVD-reduced term-document matrix
	        1. performance comparison of two stylometric features, namely “Average Sentence Length” and the “Honore Function”
      1. Cross Lingual Semantic Approach - semantically annotated graph model 
	        1. graph characterizes a document and similarity between graphs represents similarity between documents
      1. Regular cross lingual - combines lexical and syntactic features such as character-n-grams without taking semantic annotations into consideration
	        1.  translate a document before applying a monolingual detection approach.
      1. Language model - a tf-idf vector-based approached with a vector space model. 
	        1. It also takes type of plagiarism, by analyzing the length of a suspicious section with regard to summarized plagiarism
  1. Dataset: PAN PC competition corpora
  
* Paper Title: [Retrieving plagiarized documents using semantic similarity](https://www.researchgate.net/profile/Fawad_Hussain/publication/281775287_On_retrieving_intelligently_plagiarized_documents_using_semantic_similarity/links/5d023dc492851c874c62a60e/On-retrieving-intelligently-plagiarized-documents-using-semantic-similarity.pdf)
  1. Solution: 
      1. semantic similarity measure with a Nearest Neighbor (NN) search for content of document
      1. Modified X-Sim algorithm – a supervised pruning of the similarity values, and term weighting
      1. Multi class SVM based classifier for Titles
      1. use a) and c) for plagiarism index
  1. Dataset:  20 Newsgroup corpus,LingSpam collection, the Reuters-21578 corpus, and the TDT

* Paper Title: [Detecting singleton review spammers using semantic similarity](https://arxiv.org/abs/1609.02727)
  1. Publication: WWW 2015
  1. Problem:  detecting fake reviews written by the same person using multiple names, posting each review under a different name
  1. Solution:
      1. semantic similarity between words to the reviews level.
	        1. wordnet + cosine similarity of POS tokens
      1. n topic modeling and exploits the similarity of the reviews topic distributions using two models: 
	        1. bag-of-words which included a restricted set of POSs
	        1. bag-of-opinionphrases - splits a review into aspect-sentiment pairs, and these pairs are then used in the LDA model, instead of the document words.
  1. Dataset: Yelp , Trustpilot, OTT
 
 * Paper Title: [Toward validation of Textual information Retrieval techniques for software weakness](https://arxiv.org/abs/1809.01360) 
  1. Publication: DEXA-2018
  1. Problem: Map unstructured software vulnerability information to distinct software weaknesses ( security related mistake in software development)
  1. Solution:
      1. 5 similarity metrics based on Tf-Idf variant to create weakness matrix
      1. similarities between the weakness matrix and vulnerabilities is with cosine similarity 
  1.Dataset : NVD
  
* Other Approaches
  1. [Microsoft Deep Semantic Similarity Model](https://www.microsoft.com/en-us/research/project/dssm/) - use siamese architectures and cosine similarity to rank query document pairs using sent2vec
  1. simpler approach to document similarity is to concatenate the semantic representations of the two documents and train a binary classifier to determine whether two given documents are similar or dissimilar.
  1. Vector based - Word embeddings and similarity
      1. Fast Embeddings, Word2vec, Glove, Elmo
