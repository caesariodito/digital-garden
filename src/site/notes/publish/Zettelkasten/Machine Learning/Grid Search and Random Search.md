---
{"dg-publish":true,"dg-path":"Zettelkasten/Machine Learning/Grid Search and Random Search.md","permalink":"/zettelkasten/machine-learning/grid-search-and-random-search/","dgHomeLink":true,"dgShowBacklinks":true,"dgShowLocalGraph":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgLinkPreview":true,"dgShowTags":true,"noteIcon":1}
---


created:: 2023-09-23T22:05:50
up:: [[publish/Zettelkasten/Machine Learning/Hyperparameter Optimization\|Hyperparameter Optimization]]
tags:: #🌱 #machine-learning

Grid and Random search are both ways to do [[publish/Zettelkasten/Machine Learning/Hyperparameter Optimization\|Hyperparameter Optimization]]. Examples you have multiple configs or settings to try,

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/machine-learning/hyperparameter/#1tjq7j" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



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

</div></div>


with **grid search**, you will sequentially try each value and see what is the best config for the best result. This usually takes a long time to do because we literally explore each value **one by one**.

with **random search**, you will take each one *knob* randomly for `n` times and see what is the best outcome of all those multiple sequence of trying. This method doesn't took that much time compared to grid search.

this two methods is limited and biased because we don't know if there're any other values that can be better than your current config. Below is the example.

![[Pasted image 20230923222519.png\|300]]

**in conclusion**, both ways aren't that good compared to other advanced [[Hyperparameter Optimization Techniques\|Hyperparameter Optimization Techniques]].

## Related:

- [[Hyperparameter Optimization Techniques\|Hyperparameter Optimization Techniques]]
- [[publish/Zettelkasten/Machine Learning/Hyperparameter Optimization\|Hyperparameter Optimization]]
- [[publish/Zettelkasten/Machine Learning/Hyperparameter\|Hyperparameter]]

---
# Resources

- #### David, D. (2020). Hyperparameter Optimization Techniques to Improve Your Machine Learning Model’s Performance. Retrieved from https://www.freecodecamp.org/news/hyperparameter-optimization-techniques-machine-learning/. Accessed 23 Sept. 2023.