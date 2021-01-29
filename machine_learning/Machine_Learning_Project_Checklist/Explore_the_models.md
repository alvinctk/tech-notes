## Explore (Shortlist) Promising Models

> If the data is huge, try to sample smaller training sets, so you can train
> many different models in a reasonable time. 

> Beware that this penalizes complex models such as large neural nets or Random
> Forests.

> Try to automate these steps as much as possible. 

1. Train many quick-and-dirty models from different categories (e.g., linear,
   naive Bayes, SVM, Random Forest, neural net, etc.) using standard
   parameters.

2. Measure and compare their performance.
- For each model, use N-fold cross validation and compute the mean and standard
  deviation of the performance measure on the N fold. 


3. Analyze the most significant variables for each algorithm.

4. Analyze the types of errors the models make.

- What data would a human have used to avoid these errors?

5. Perform a quick round of feature selection and engineering.

6. Perform one or two more quick iterations of the five previous steps.

7. Shortlist the top three to five most promising models, preferring models that make different types of errors.

[Back to Machine Learning Project Checklist](./README.md)
