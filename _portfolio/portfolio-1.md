---
title: "Video Question Answering"
excerpt: "Video Question Answering was a class project that I had worked on as part of the Question Answering Class (11-797). 
For this project, I explored how temporal information in videos can be leveraged to improve Video Question Ansering <br/><img src='/images/VideoQA.png' width='30%'> <br/><!--Link to VideoQA.pdf--> [Project Paper](../files/VideoQA.pdf)"
collection: portfolio
---

Video question answering (VideoQA) is the task of answering questions about a Video. 
To address this, We looked into methods for improving representations for VideoQA. More specifically, our research focuses on the following questions: 
    1) How can we leverage the knowledge of frames being close together in time to improve the representations?
    2) How can we leverage captions in VideoQA tasks?
By leveraging similar representations for clips that occur close together in a video improves performance for questions that require knowledge of the timing of an action.
In addition, we converted the VideoQA taks into Text-only Question Answering task by generating captions for the videos, and experimented with different methods of Caption generation.

## AGQA

The (Action Genome Question Answering)[https://cs.stanford.edu/people/ranjaykrishna/agqa/] dataset contains Video, Question, Answer tripplets with 4 Million Question Answer pairs, 10,000 different videos, and and 174 answer choices. The Videos are from the Charades dataset (avg len 30 sec), where the Videos are annotated with scene graphs about the actions that occur in the video. Based on the Scene Graphs, questons are generated. This dataset was chosen as the top performing models on previous benchmarks showed a significant drop in performance. The dataset also contains multiple splits that can evaluate the models on different abilities such as generalizability and compositionality.

## Creating a temporal loss

The temporal loss refers to a penalty for changing representations between frames. I experimented with an using the L1, L2 losses, and the forbenious norm. These would penalize different aspects of changing representations between frames, so all of them were experimented with. To apply the loss, intermediate features within the model were selected and the change between them was added to the CrossEntropy loss for the QA task. Just using the L2 loss, there was an statistically significant improvement in answering questions about action questions, and the ordering of actions. When hyperparameter tuning was applied to the combination of losses, the overall model improved a few percentage points in accuracy. 

## Text-only Question Answering

The second part of the project was to convert the VideoQA task into a Text-only QA task. To do so, we used the charades dataset to train a model for caption generation. We first experimented with using the golden captoins (existing human captoins), and then experimented with using the generated captions. With the golden captions, we observed that the T5 model outperformed the HCRN model performance, and while the generated captions experienced a significant performance drop, they still predictive power. 
