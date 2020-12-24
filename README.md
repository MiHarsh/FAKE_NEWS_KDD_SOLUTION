# Fake News Detection

Fake News Detection for social media posts/articles is nowadays becoming a tricky and difficult task. Classifying any news as fake or not, without considering the whole context is a futile task because it relies on total context and not just a part of it. In this Competition,the dataset contained very large texts. Advanced models like RoBERTa have limitations of maximum words , so I have divided the whole text into smaller splits that are overlapping. This model showcases competitive performance on the Fake News Detection shared task-organized on Kaggle (in partnership with SIGKDD) and achieved an accuracy score of 0.83733 on the private leaderboard and secured the second position.

#### Data 
The dataset used for this study was provided in the shared task on Fake News Detection, organized on Kaggle. It included a training set and a test set. The train set ranges from 4 words to a maximum of 17121 words, and the test set ranges from 1 to 17520 words. Both the datasets consisted mainly of long texts, with most examples falling under 512-word count length (as shown in Figure 1). 

![Data Distribution](https://github.com/MiHarsh/FakeNewsDetection_MicrosoftKDD/blob/master/Visuals/DataDistribution.png?raw=true)

#### Method Used
For using the complete context, we broke it into smaller parts of fixed lengths. We labeled all of the parts the same as the original label of the context. Here, a problem which arises is that some parts may not correspond to the original label, i.e., if the original label given to the whole context is fake, some smaller parts of the context might not be particularly fake. So, to overcome this problem, we used some of the contexts from the previous split into the current one so that the overall label of the context remains the same. In this way, we preserved the meaning of the example and also used it completely. We got the best results when the length of the splits were kept 150 and intersecting words was kept as 22.

![model](https://github.com/MiHarsh/FakeNewsDetection_MicrosoftKDD/blob/master/Visuals/Model.png?raw=true)

#### Results

![result table](https://github.com/MiHarsh/FakeNewsDetection_MicrosoftKDD/blob/master/Visuals/Results.png?raw=true)
