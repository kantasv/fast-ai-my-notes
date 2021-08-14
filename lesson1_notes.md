1. Do you need these for deep learning?  

   - Lots of math T / F
   - Lots of data T / F
   - Lots of expensive computers T / F
   - A PhD T / F  

   Ans: F, F, F, F respectively. Thought it seems lots of data is good thing as long as these data are proper datasets.
   
1. Name five areas where deep learning is now the best in the world.  

   Ans: Image recognition, text translation, healthcare, recommendtation systems, and Genome analysis to name a few...

1. What was the name of the first device that was based on the principle of the artificial neuron?  
   
   Ans: Perceptron, or Mark I Perceptron.

1. Based on the book of the same name, what are the requirements for parallel distributed processing (PDP)?
   
   Ans:  
   A set of processing units  
   A state of activation  
   An output function for each unit  
   A pattern of connectivity among units  
   A propagation rule for propagating patterns of activities through the network of connectivities
   An activation rule for combining the inputs impinging on a unit with the current state of that unit to produce an output for the unit  
   A learning rule whereby patterns of connectivity are modified by experience  
   An environment within which the system must operate  


1. What were the two theoretical misunderstandings that held back the field of neural networks?  
   Ans:  
   - One layer neural nets cannot approximate even simple functions, e.g. XOR, thus neural nets aren't usable in real situations, which is kinda misleading because adding layers may solve the situation in theory.    
   - Neural nets can do anything by adding more and more layers (two layers can approximate any kinda functions in theory), which was not necessarily the case considering computational complexity back in the day until the end of *Second AI Winter*.  

1. What is a GPU?  
   Ans:
   It stands for Graphics Processing Unit, which was originally used for game graphics. Later on, it turns out GPU is also applicable even in machine learning tasks, since GPU has way more processing units than CPU, enabling pararell processing in many small units in learning tasks.

1. Open a notebook and execute a cell containing: `1+1`. What happens?
   Ans: It gives me 2, which is the result of calculation 1+1 by Python.  

1. Follow through each cell of the stripped version of the notebook for this chapter. Before executing each cell, guess what will happen.
   Ans: DONE
1. Complete the Jupyter Notebook online appendix.
   Ans: DONE  
1. Why is it hard to use a traditional computer program to recognize images in a photo?  
   There was no good representation of parameters and features of an object back in the day. Even we had some techniques to extract some features to specific types of object, it is only applicable to these specific items, not being generalized. This approach,  often called feature engineering, depends on engineers understanding of some specific object. However, now we have neural nets, which takes care of even feature extraction automatically. This remarkably accelerated the area of computer vision.

1. What did Samuel mean by "weight assignment"?  
   Ans: In his statement, weight assignment is a set of parameters to define operation to learn from inputs and gives you outputs. For every weight assignment has its performance, and a program could improve such weights by trying to maximize paformance.

1. What term do we normally use in deep learning for what Samuel called "weights"?
   Ans: Parameters  

1. Draw a picture that summarizes Samuel's view of a machine learning model.
   Ans: DONE

1. Why is it hard to understand why a deep learning model makes a particular prediction?

  Ans: This is because a deep learning model could have multiple layers, and each layer have considerable amount of parameters, obscuring what is going on each steps of prediction as well as the process of learning, compared to traditional machine learning methods, e.g., logistic regression. Meanwhile, in some cases, it is possible to interprete deep learning's complex parameters; The concept is often called *Explanable AI*. In 2013, a technique to visualize convolitonal neural nets was introduced.(Matt Zeiler et al.)

1. What is the name of the theorem that shows that a neural network can solve any mathematical problem to any level of accuracy?

  Ans:  Universal Approximiation Theorem

1. What do you need in order to train a model?
   Ans:
   This is not an easy question, but to name key ingredents from my point of view:
   - Architecture, e.g. CNNs
   - Dataset to feed your model, often includes labels 
   - performance measures e.g. loss function
   - optimizer and its hyperparameters

1. How could a feedback loop impact the rollout of a predictive policing model?

   Ans:
   First, datasets of the local crimes are fed into a machine learning model. Suppose dataset is biased; some specific race groups in some areas may have more tendency according to these stats. Unfortunately, even though such data reflects officer's biases and many other factors, model may output results that areas with such groups has higher crime probability. Based on the insight, local police may increase resources in these specific areas. As a conseqence, the more crimes are observed there, and affects next year's stats. Then, such stats could be fed into next machine learning models, and similar steps from may repeated over and over. This is one of the ethical issues that we face when we apply machine learning models into real life.

1. Do we always have to use 224×224-pixel images with the cat recognition model?

   Ans:
   Not necessarily. 224x224 format is a convention in computer science fieald. You could use other sizes of images. However, you have to consider the relationship between sizes and computational resources.

1. What is the difference between classification and regression?

   Ans:
   Classification is to classify some data into multiple groups, and the dataset fed into this task does not requires labels. For example, companies might want to use classificaton to segment users based on ther activities, and figure out what kind of segment to approach as business decision making.
   Meanwhile, regression is to predict some quantitative infomation based on the past data with labels. For example, given people's social backgrounds, predicting someone's longevity could be an example of regression.
1. What is a validation set? What is a test set? Why do we need them?
   Ans:
   Valiadtion set is a part of dataset that is used to measure how good the model is. Training set does not include validation set. This is to prevent model from memorizing dataset and failing to generalize to new dataset. In other words, this prevents overfitting, which I will explain later on this page.
   Test set is similar to validaton set, but it is separeted from even ourselves to avoid creating biased models unconsicously. In other words, this prevents overfitting that happens due to modeler's side.

1. What will fastai do if you don't provide a validation set?

   Ans: Fastai automatically grab 20% of dataset by default if no validation set specified, and it treat these data as validation set, hiding such dataset from the process of learning.

1. Can we always use a random sample for a validation set? Why or why not?
   Ans:
   We cannot always use such random sampling. This is particularly problematic when we deal with time series data. In this case, time axis have important imformation, so reducing continuity by random sampling over time axis could devastate such information. In this case, treating recent part of data as test set and taking the rest as training set, could be one of the alternatives, rather than random sampling. 
1. What is overfitting? Provide an example.
   Ans:
   Overfitting is a situation where a model learns specific dataset's feature too specifically, and fails to generalize to unknown datasets. For example, suppose fitting a simple sine curve with some random noises with some polynomials. If the model adapt to the noized dataset too much, it could be learn outliers as important feature as other normal lines. This could give us less loss function value for the training set, but when humans look at the approximated curve, it could have crazy values outside the range of available training sets. To avoid this, validation set and test set are helpful. 

1. What is a metric? How does it differ from "loss"?

   Ans: Metric is a measure of how good a model is, specifically for human beings. It is more readable, easier to understand for us. For example, *accuracy* is a metric to describe how accurately the model classifies with the validation set. Also, *error rate* is similar but is for describing how incorrectly the model classifies the validation set. Meanwhile, loss function is for model and optimizers to learn from the training set, and it is not necessarily usable as metric.  

1. How can pretrained models help?  
   Ans: Pretrained models have been already trained for tasks that datasets are provided. As long as the type of problem is similar, i.e. detecting cat's images from dog detection pretrained model, you may fine-tune parameters, and possibly save your time, rather than trainig a model from scratch. In image recognition, for example, pretrained models already have edge, gradient, and color information, and these information is generally helpful for many image recognition tasks.  Pretrained models are not always perfect, since they are trained on different tasks after all, but according to the fastbook, its capabilities have been underestimated by many people in both academica and companies, leading to the wrong assumption: "We have few resources, so we can't use deep learning!"

1. What is the "head" of a model?  
   Ans:  When we use pretrained models for different but similar tasks, the last layer will be removed because that is very unique to the original training task. We replace it with different layer(s) called *head*. This layer(s) is typically randomly weighted with appropriate sizes, and weights are updated regarding to the dataset of new task.

1. What kinds of features do the early layers of a CNN find? How about the later layers?
   Ans: Early layers could learn very basic edges, shapes. Meanwhile, tha later layers could learn more complex shapes that consists of building blocks of earlier layers, even human faces for example.

1. Are image models only useful for photos?
   Ans: Image models could be applied to various tasks, such as fraud detection, malware detection and sound classification. This is possible by converting non image dataset into image representation, and feeding them into image models. Sometimes you could come up with world-class models with this creative approach.

1. What is an "architecture"?  
   Ans:  A template of model that we pass inputs and weights, and fit.  
1. What is segmentation?
   Ans:  In image recognition, segmentation means segment multiple area based on semantics. For example, An autonomous car model needs to understand which area in its camera corresponds to human beings, road, or other objects.

1. What is `y_range` used for? When do we need it?
   Ans: For models that predictions are continuous value, not categories, we have to tell fastai these range information. In that case, we use `y_range`.

1. What are "hyperparameters"?  
   Ans: Higher level of parameters, that should be decided before starting learning. This special parameters gorvern lower level parameters, often called weights in neural nets for example, thus hyperparameters should be carefully chosen.

1. What's the best way to avoid failures when using AI in an organization?  
   Ans: You should clearly decide metrics, and properly manage validation set, and test sets, so that actual model the comes out can be usable in real situation. For example, it is pereferable to hide some portion of data from AI engineers, and you should test the model that comes out after the engineers made models. This is because they can state the model works well for the task of your interest, but in reality, thay may mislead you by overfitted and *seemingly* perfect model, or they made overfitted model without knowing it. Another factor is to set a baseline, such that model your team is working on should outperform. 