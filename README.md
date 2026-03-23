

You may choose to perform classification on any sequential dataset (text, audio, etc.) or image dataset you like using a pre-trained transformer. For example, you could choose a text dataset. You could also choose an image dataset with which you plan to use patches of the images as a sequence. Or time-series data. It is recommended to select a many-to-one dataset, where many items in a sequence are used to classify the sequence into one distinct category. Several examples are given below that might be possible. However, it is up to you to choose which data you would like to analyze. A general guideline rubric is also given.

As a reminder, LLMs (like ChatGPT, Mistral, and others) should NOT be used for any text generation or text refinement. These tools should only be used for coding (and perhaps some data generation tasks, depending on your application). Using an LLM for any text descriptions/refinement violates the honor code for this course. 

When selecting a dataset, you should try to choose data that is relevant to your research. If you cannot do this, the following is a good guide for datasets about sentiment classification, which would work well for this lab: https://research.aimultiple.com/sentiment-analysis-dataset/Links to an external site. 

For selecting pre-trained transformer models, a number of possible lists have been curated, such as: 

This is not an exhaustive list. Hugging face transformers are released on a rolling basis, pre-trained for a number of tasks. 
Hugging Face Text transformers: https://huggingface.co/transformers/v3.3.1/pretrained_models.htmlLinks to an external site.Links to an external site.
Hugging Face ViT: https://huggingface.co/docs/transformers/model_doc/vitLinks to an external site.Links to an external site.
Keras text Transformers: https://keras.io/guides/keras_nlp/transformer_pretraining/Links to an external site.
Keras ViT: https://github.com/faustomorales/vit-kerasLinks to an external site.
Or any other transformer you want to use as a base model. 
NOTE: It is advised to choose a foundational model that is not too computational, as you are required to perform fine tuning in this lab. Therefore, choosing a more modest foundational model (if you have hardware limitations) is acceptable. 
General Grading Rubric:
The following grading rubric will be used:

[2.0 points] Give an overview of the dataset you have chosen to use. The overview should be comprehensive. Minimal examples of questions that should be answered are shown below. Depending on your dataset, an expanded explanation could be needed: 

What is the classification task? What business or policy case does it solve? Is this multi-task? Explain.
What is the feature data? How is it stored? Who collected the data? Why? When? Is the data multi-modal?
What evaluation criteria will you be using and why? Why does this support the business or policy case?
[2.0 points] Describe the foundational model that you will be using to transfer learn from in your own words.   What task(s) was this foundational model trained upon? Describe the foundational model as concrete under a playground. Explain if the new task is within the same domain, across domains, etc.  Include specifics about the architecture used in the foundational model, storage, computation, etc.

[1.0 points] Split your data into training and testing and define your loss function.   Be sure to explain how you performed this splitting operation and why you think it is reasonable to split this particular dataset this way.   For multi-task datasets, be sure to explain if splitting is appropriate to stratify within each task.  If the dataset is already split for you, explain how the split was achieved and how it is stratified.   For the Loss function used, explain why this is appropriate.   Describe if there is a single loss function or multiple losses being combined. 

[2.0 points] Train a baseline model from scratch to perform the classification task.   That is, do NOT use transfer learning for this step--you are training a model to see the baseline performance.   Verify the model converges (even if the model is overfit). Note: This should NOT mirror the foundational model. It does NOT even need to be a transformer--this model may be far less computational to train (perhaps a random forest or variant). 

[2.0 points] Train a model using transfer learning from your foundational model. Verify that the new model converges. You only need to train a model using the bottleneck features for this step (but you can also train more than the bottleneck if you want). 

[2.0 points] Perform fine tuning upon the model by training some layers (or all layers) within the foundational model. Verify that the model converges. Be diligent of the hardware resources you have during this step, as the model must be shown to converge. 

[4.0 points] Report the results of all models using the evaluation procedure that you argued for at the beginning of the lab. Results should be described comprehensively. Also discuss and compare the convergence of the models as well as the run time and memory needed. Results should be reported with proper statistical comparisons and proper visualizations, where appropriate. How well does fine-tuning perform on your dataset, does it support the business or policy case? Are there advantages or limitations? 
