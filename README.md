# Cloud-Technologies---Mapper-Reducer-and-TF-IDF
Cloud Technologies - Mapper, Reducer and TF-IDF


# Data Extraction and Data Loading using Pig and Hive


# TF-IDF Calculation using Map Reduce:
Implementation of TFIDF in Hadoop using Python as three phases.

# - Phase One:
Mapper  : ((word, User_ID), 1)
Reducer : ((word, User_ID), word_count_in_doc)

# - Phase Two:
Mapper  : (User_ID, (word, word_count_in_doc))
Reducer : ((word, User_ID), (word_count_in_doc, words_in_doc))

# - Phase Three:
Mapper  : (word, (User_ID, word_count_in_doc, words_in_doc, 1))
Reducer : ((word, User_ID), tf-idf)

# - Hadoop commands for TF-IDF Calculation:
hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -file "Mapper Path" MapperPhaseOne.py  -mapper "python MapperPhaseOne.py"  -file "Reducer Path" -reducer  "python ReducerPhaseOne.py" -input "Program Input path and file_name" -output  "Program Output path and file_name"
