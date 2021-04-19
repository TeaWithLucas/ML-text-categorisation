Machine learning text categorisation for bbc dataset
# Instructions of usage
1. Go to [https://colab.research.google.com/github/TeaWithLucas/ML-text-categorisation/blob/main/ml_text_cat.ipynb](https://colab.research.google.com/github/TeaWithLucas/ML-text-categorisation/blob/main/ml_text_cat.ipynb)
2. (Optional) Change any of the Setting as you desire in the setting heading (details below)
3. Run all the code using Runtime > Run all (Ctrl+F9) or run all the code sequentially manually
4. View the execution section to see the excution process and outputs and the subheading Evaluation for the final results
5. (Optional) Adjust any of the Settings as you desire
6. (Optional) Run the Settings and Execution section and review the results

# Settings
In the setting section are various variables which you can use to change how the program works, they are as follows
* zipped_data - the name of the zip file containing the datasets
* data_path_folder - directory of the category folders
* test_size - test set split in percent (training split is the remaining amount)
* dev_size - development set split in percent (training split is the remaining amount)
* token_max - max amount of most frequent tokens allowed in a volcabulary
* tagged_max - max amount of most frequent tagged words allowed in a volcabulary
* ngram_max - max amount of most frequent ngrams allowed in a volcabulary
* feature_sets_enabled - list of feature sets to be used in the model, they are explained and listed in the feature sets section below
* word_tags - part-of-speach tags allowed in the word_tagged feature set
* scoring_model - Choose the feature selection scoring model 
* model_choices - a set of tuples containing a model class and the chosen parameters for that class
* list_num_features - a list of possible number of top scoring features allowed

# feature sets
The following are feature sets that use normalised frequency counts:
* 'gen_basic' - uses NLTK tokenised words to generate features based on those words
* 'bigram' - uses sklearn's default word tokeniser to generate features based on pairs of words
* 'trigram' - uses sklearn's default word tokeniser to generate features based on triplet of words
* 'word_tagged' - uses NLTK part-of-speach tagged words, filters them with the list in the word_tags setting, to generate features based on those tagged words
* 'verb'- uses NLTK part-of-speach tagged words, selects only verb tagged words, to generate features based on those tagged words
* 'adj'- uses NLTK part-of-speach tagged words, selects only adjective tagged words, to generate features based on those tagged words
* 'adjverb' - uses NLTK part-of-speach tagged words, selects only verb and adjective tagged words, to generate features based on those tagged words
The following are feature sets that use pretrained embedding models
* 'embedding_glove' - uses the pretrained model ‘glove-twitter-25’ to generate features
* 'embedding_fasttext' - uses the pretrained model ‘fasttext-wiki-news-subwords-300’ to generate features
* 'embedding_word2vec' - uses the pretrained model ‘word2vec-google-news-300’ to generate features
any embedding models listed at [https://github.com/RaRe-Technologies/gensim-data#models](https://github.com/RaRe-Technologies/gensim-data#models) can be used using the format `embedding_[model name]`
