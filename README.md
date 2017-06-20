
# Spam Detection Using Weka

<h2>Problem Statement</h2>
We want to check that email is spam or not through text classification in WEKA.
<h2>Introduction</h2>
Every day E-mail users receive hundreds of spam messages with a new content, from new addresses which are automatically generated by robot software. To filter spam with traditional methods as black-white lists (domains, IP addresses, mailing addresses) is almost impossible. Application of text mining methods to an E-mail can raise efficiency of a filtration of spam. Also classifying spam messages will be possible to establish thematic dependence from geographical.

<h2>DATASET</h2>
We have 5180 emails as dataset in three folders norm for normal, ham for harm and spam for Spam. Dataset features are as follows.
1.	A particular word or character was frequently occurring in the e-mail. 
2.	The run-length attributes (55-57) measure the length of sequences of consecutive capital letters.
<b>Source: </b><a href="http://www2.aueb.gr/users/ion/data/enron-spam/">Spam Email Datasets</a>
<h2>Implimentation</h2>
<h3>C4.5(J48) Algorithm</h3>
We are using C4.5 algorithm known as j48 algorithm in WEKA. C4.5 is an algorithm used to generate a decision tree developed by Ross Quinlan. C4.5 is an extension of Quinlan's earlier ID3 algorithm. The decision trees generated by C4.5 can be used for classification, and for this reason, C4.5 is often referred to as a statistical classifier. 
It became quite popular after ranking #1 in the Top 10 Algorithms in Data Mining.<br>

A decision tree is a graph that uses a branching method to illustrate every possible outcome of a decision. Programmatically, they can be used to assign monetary/time or other values to possible outcomes so that decisions can be automated.

Following is example decsion tree.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/25.JPG">
<h3>Naive Bayes Algorithm Implimentation</h3>
We are also comparing results with results get from Naive Bayes. It is a classification technique based on Bayes' Theorem with an assumption of independence among predictors. In simple terms, a Naive Bayes classifier assumes that the presence of a particular feature in a class is unrelated to the presence of any other feature.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/24.png">

<h2>How to Run</h2>
<b>Source: </b><a href="http://www.cs.waikato.ac.nz/ml/weka/downloading.html">Downloading and installing Weka</a>
<h3>1.	Normalize Data</h3>
The dataset we get was in 5180 text files as shown in following screenshots.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/1.png">
(3 Folders in one Folder)
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/2.png">
 (Insight one folder)
 <img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/3.png">
 (One File)<br>
 As you can see in above screenshots that data is not normalized and well manage and we cannot give it as input to WEKA. We need all data in one arff file to give it WEKA for training. So for this purpose we use following command in command line interface of WEKA. 
“java weka.core.converters.TextDirectoryLoader –dir F:/Spam_Mails > F:/Output.arff”
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/4.png">
The output arff file is following.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/5.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/6.png">
Now data is normalized. So we will give it to the WEKA for further pre-processes as follows.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/7.png">
<h3>C4.5(J48) Algorithm Implimentation</h3>
Now we will select and apply our classifier as follows. 
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/8.png">
We are using every frequent word as feature so here we will break string in word vector as follows.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/9.png">
First we train data as follows by selecting train data set option and we get following results.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/10.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/11.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/12.png">
Here we get 98% accuracy. Than we further train it on different split percentages and get following results.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/13.png">
On 66% split percentage we get 93% accuracy. 
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/14.png">
On 80% split percentage we get 94% percent accuracy. 
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/15.png">
On 90% split percentage we get 89% accuracy.<br>
Now we decided to test our model, so we make test dataset from our own email ids as shown in following screenshot. 
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/16.png">
Now we give this test dataset to our trained model and we get following predictions about this dataset.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/17.png">
Our model give prediction as shown in above screenshot. 
<h3>Naive Bayes Algorithm Implimentation</h3>
I repeat the same procedure with Naïve Bayes shown in following snapshots.
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/18.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/19.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/20.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/21.png">
<img src="https://github.com/waleedalinizami/IML-Smester-Project/blob/master/img/22.png">
It shows different results with good accuracy. 
<h2>References</h2>
[1] A. Anderson, M. Corney, O. de Vel, and G. Mohay."Identifying the 
Authors of Suspect E-mail". Communications of the ACM, 2001.<br> 
[2] Shlomo Hershkop, Ke Wang, Weijen Lee, Olivier Nimeskern, German 
Creamer, and Ryan Rowe, "Email Mining Toolkit Technical Manual". 
(June 2006) Department of Computer Science Columbia University. <br> 
[3] Bron, C. and J. Kerbosch. "Algorithm 457: Finding all cliques of an 
undirected graph." (1973). <br> 
[4] Ding Zhou et al and Ya Zhang, "Towards Discovering Organizational 
Structure from Email Corpus". (2005) Fourth International Conference on 
Machine Learning and Application. <br> 
[5]  Giuseppe Carenini, Raymond T. Ng and Xiaodong Zhou , "Scalable 
Discovery of Hidden Emails from Large Folders". Department of 
Computer Science, University of British Columbia, Canada. <br> 
[6] Hung-Ching Chen el al, "Discover The Power of Social and Hidden 
Curriculum to Decision Making: Experiments with Enron Email and 
Movie Newsgroups". Sixth International Conference on Machine 
Learning and Applications. <br> 

