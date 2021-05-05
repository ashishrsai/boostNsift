# boostNsift
Implementation of BoostNSift Method Level Bug Localization Technique

# Introduction:
BoostNSift is a new, method-level, Information-Retrieval based bug localization technique. It exploits the important information in queries by ‘boost’ing that information as bug localization starts and then ‘sift’s the identified code elements, based on a novel technique that emphasizes the code elements’ specific relatedness to a bug report over its generic relatedness to all bug reports.

# How to Use:
  1)-Prepare the method corpus and queries (bug reports). We provided Corpus-Generater and Corpus-Preprocessor for getting and preprocessing source code and queries. These   projects are provided separately to generalize the use of BoostNSift with different type of parsing and preprocessing techniques. Required format of these files can be seen in files located in Dataset folder.
  
  2)-To perform BoostNSift analysis, import the BoostNSift project (preferably in eclipse using Java 11). Then, open the file BoostNSift.java and provide the paths to the input files required i.e. title of the bugs, descriptions of the bug, comments in the bugs and corpus of the methods. Note that lib directory in project contains all the jar files required in BoostNSift. Also note that in our dataset, comments are already added in descriptions, hence to weight comments two time higher we just incorporated them in technique one more time separately (See comments written in BoostNSift.java for details).
  
  3)-BoostNSift will provide you the intermediate results to assess them with all possible evaluation measures. To assess the results using the evaluation measures have used in our paper, please run the python scripts attached (BoostNsiftEvaluationScript.py file is main file which will make use of rank_metrics.py file). That script will required the intermediate result (created in previous step) and Answer Matrix (given in dataset folder) files as input.
  
# Dataset Descriptions:
--Each line of corpus file contain the corpus of each method in software system. IMPRTANT: Line number where a method is located is considered as 'id' of that method

--Each line in queries files contain title, description+comments or comments

--Both above mentioned files contain data in pre-processed format: following the pre-processing steps describe in paper

--IMPRTANT:Each line in AnswerMatrix file represent the ids of the methods fixed against each query. Here, line number corresponds to the query number (line in queries file) and id number of method is the line number of the method located in corpus file



