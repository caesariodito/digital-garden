---
{"dg-publish":true,"dg-path":"Zettelkasten/Machine Learning/Hyperparameter.md","permalink":"/zettelkasten/machine-learning/hyperparameter/","dgHomeLink":true,"dgShowBacklinks":true,"dgShowLocalGraph":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgLinkPreview":true,"dgShowTags":true,"noteIcon":1}
---


created:: 2023-09-23T21:43:23
up:: [[Machine Learning\|Machine Learning]]
tags:: #🌱 #machine-learning

In the context of [[Machine Learning\|Machine Learning]], hyperparameter is some kind of *knobs* that you can turn to left or right - that has impact to the result/output.
{ #eemz2u}


Each *knob* will result to different impact, turning the first *knob* to right might increase the performance, but when you turn the second *knob*, it might decrease the performance.

The simple word for hyperparameter is `config` or `settings`. One note that hyperparameter is different from [[publish/Zettelkasten/Machine Learning/Parameter\|Parameter]].

It is **internally not connected** to the machine/model.

Here is an example of the hyperparameter:
```python
# xgb hyperparameter
parameters = {  
	"n_estimators": [10, 50, 100],  
	"subsample":[0.6, 0.8, 1],  
	"learning_rate":[0.01, 0.1, 0.5, 1],  
	"gamma":[0.01, 0.1, 1, 5],  
	"colsample_bytree":[0.5, 0.7, 0.9, 1],  
	"alpha":[0, 0.1, 0.5]  
}
```
{ #1tjq7j}


## Related:

- [[Machine Learning\|Machine Learning]]
- [[publish/Zettelkasten/Machine Learning/Parameter\|Parameter]]

---
# Resources

- #### Nyuytiymbiy, K. (2022). Parameters and Hyperparameters in Machine Learning and Deep Learning. Retrieved from https://towardsdatascience.com/parameters-and-hyperparameters-aa609601a9ac. Accessed 23 Sept. 2023.