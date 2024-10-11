# Online Average Happiness Maximization Queries over Data Streams
This repository contains source code of our paper "Online Average Happiness Maximization Queries over Data Streams" which introduces two approximation algorithms (ThresholdOnline and SieveOnline) for the online average happiness maximization query (Online-AHMQ) problem. 

# Datasets
This repository provides 2 synthetic datasets and 3 real datasets used in our experiments, as follows:

* IND: a synthetic dataset generated as described in [S. Börzsöny, D. Kossmann, and K. Stocker, “The skyline operator,” in ICDE, 2001, pp. 421–430]. It is a set of uniform points on the unit hypercube where different attributes are independent of each other.

* Anti-Cor: a synthetic dataset generated by the synthetic dataset generator [S. Börzsöny, D. Kossmann, and K. Stocker, “The skyline operator,” in ICDE, 2001, pp. 421–430.]. The dataset contains 10,000 random data points with 4 anti-correlated attributes.

* Tweet: a real dataset for streaming applications and we adapted it for our comparison. The data points describe tweets delivered during a certain period and the goal is to select the most popular tweets of a fixed size. After pre-processing, we selected 12,197 tweets described by 7 attributes, namely TweetID, UserID, FollowerCount, FollowingCount, ReplyCount, LikeCount and RetweetCount.

* Football: a real dataset contains 2,689 football players with 3 attributes, which are goals, assists, and tackles.

* Weather: a 15-dimensional real dataset with 566,268 points, each of which consists of average monthly precipitation totals and elevation at over half a million sensor locations.

# How to reproduce the experiments in our paper
Our experiments were conducted on a machine running Ubuntu 20.04 LTS. We run our experiments on 2 synthetic datasets and 3 real datasets, and all algorithms were implemented in C++. We provide the explanations of the files as follows:

## Main function
- File "src/main.cpp": is used to conduct comparative experiments for Online-AHMQ problem and output results.

## Datasets
- Folder "dataset": contains datasets as introduced above.
- Note: Some datasets (weather and Anti-Cor_3_1000000) are larger than 25M which are not permitted to upload. We are glad to share them on request.

## Useful tools
- Files "src/IOUtil.h" and "src/IOUtil.cpp": are used to load the datasets.
- Files "src/Point.h" and "src/Point.cpp": are used to represent the elements in the datasets and process some related calculations.
- Files "src/RandUtil.h" and "src/RandUtil.cpp": are used to generate random numbers under a specific distribution.
- Files "src/RMSUtils.h" and "src/RMSUtils.cpp": are used to generate random utility functions under a specific distribution.

## Objective functions
- File "src/ObjectiveFunction.h": is the base class of the other submodular functions.
- File "src/AvgHappiness.h": is the average happiness ratio function.

## Evaluated algorithms
- File "src/SubsetSelectionAlgorithm.h": is the base class of the following algorithms.
- File "src/ThresholdOnline.h": is the first online algorithm proposed in this paper.
- File "src/SieveOnline.h": is the second online algorithm proposed in this paper.
- File "src/Greedy.h": is the offline algorithm proposed in [G. L. Nemhauser, L. A. Wolsey, and M. L. Fisher, “An analysis of approximations for maximizing submodular set functions-i,” Mathematical Programming, vol. 14, no. 1, pp. 265–294, 1978.]
- File "src/GreedyAT.h": is the online algorithm proposed in [Z. Hao and J. Zheng, “Computing online average happiness maximization sets over data streams,” in Web and Big Data - 6th International Joint Conference, APWeb-WAIM 2022, Nanjing, China, November 25-27, 2022, Proceedings, Part III, ser. Lecture Notes in Computer Science, vol. 13423. Springer, 2022, pp. 19–33.]
- File "src/Preemption.h": is the online algorithm proposed in [Niv Buchbinder, Moran Feldman, and Roy Schwartz. Online submodular maximization with preemption. ACM Transactions on Algorithms, 15(3): 30:1–30:31, 2019.]
- File "src/ThreeSieves.h": is the streaming algorithm proposed [S. Buschjäger, P.-J. Honysz, L. Pfahler, and K. Morik, “Very fast streaming submodular function maximization,” in Machine Learning and Knowledge Discovery in Databases. Research Track: European Conference, ECML PKDD 2021, Bilbao, Spain, September 13–17, 2021, Proceedings, Part III. Berlin, Heidelberg: Springer-Verlag, 2021, p.151–166.]
