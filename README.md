# ingredient-sub

## Intro
This is a machine learning project that aims to try to automatically find substitutions for ingredients in recipes. This can be useful for accessibility reasons, as some ingredients might not be readily available in certain locations or for people in certain living conditions. The main focus of this project is to research the possible applications of natural language processing techniques in non-language contexts. I worked on this project with Isabella Eriksen, Sanyam Savla, Zach Casler, and Brian Maxwell as a part of my graduate studies. The dataset was found [here](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions) and the required files to run the code are 'ingr_map.pkl' and 'RAW_recipes.csv'. The final project writeup can be found in 'Final Project Report.pdf'.

## Methodology
NLP is a field that has been increasingly studied in recent years, and is only becoming more popular with things like ChatGPT and other AI text assistants becoming widely used by the general public. One lesser-studied side of NLP though, is its possible applications in fields other than language. In this project, we used NLP techniques on ingredients in recipes to see if similar relationships could be found. Cosine similarity is a measure used in NLP to see how similar two words are, so we used this on ingredients to see if we could accurately measure how similar two ingredients are. We represented ingredients in recipes using sparse-matrices (a co-occurrence matrix and a PPMI matrix) and calculated the cosine similarities between ingredients that are often able to be replaced with one another in recipes to see if similar conclusions could be reached.

## Findings
Known ingredient substitutions correlated with statistically significantly higher-than-average cosine similarity scores. However, because of the fact that high cosine similarity scores were often found between ingredients that could not realistically be substituted for one another, we were unable to confirm our original hypothesis. This project wasn't without promise, though. Looking at lists of ingredients with high cosine similarities with one another, we were able to find strong connections and relationships between the ingredients, even though those relationships weren't always as "substitutes."

## Future Work
The most important facet of future work in this field would be to improve on the dataset that we used. Our dataset consisted of about 170,000 recipes from [this Kaggle dataset](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions). While this might seem like a lot, it is dwarfed in comparison to the corpus that are used in NLP machine learning training, which often have millions (if not billions) of documents in the dataset. This could be one of the reasons that relationships between ingredients with high cosine similarities were found, but not in the clear-cut ways that we expected. 

Inclusion of the recipe steps could also help future work. The contribution of an ingredient to a recipe can be entirely different depending on the steps in the recipe (i.e. diced raw onions versus grilled onions). Finding ways to incorporate this into the model could be useful and improve the results.

One final note in future work in this area is that more sophisticated representations of the recipes dataset could improve results. We exclusively used sparse matrix representations to represent the recipes dataset, but dense matrix representations could provide more concrete results given more time and resources.

## Files
* co_occurrence_matrix.ipynb: This notebook contains the steps we took to create the initial co-occurrence matrix
* Updated_PPMI.ipynb: This notebook contains the steps we took to create the PPMI matrix using the initial co-occurrence matrix
* cosine_similarity.ipynb: This notebook contains the steps we used to find the top cosine similarities between ingredients
* Final Project Report.pdf: This is our final report for this project, outlining in more detail our data, methodology, findings, and interpretations
