# Crowdsourced Beer Recommender System

This beer recommender system relies on ~2500 reviews scraped from beeradvocate.com.
Different brands of beer are scored based on 5 attributes provided by the user. These attributes
are what the user looks for in a brand of beer, in no order of priority

![My Image](/images/Picture1.png)

# Scoring

For the purpose of demonstration, sample attributes are taken from a list of the most
frequently occurring words across all reviews. Sample attributes are:

- Chocolate
- Dark
- Sweet
- Bourbon
- Coffee
To begin with, the cosine similarity scores between the desired attributes and reviews are
calculated for each review. Then, the similarity scores are averaged across reviews for each
brand and stored as `similarity_score`.

![My Image](/images/Picture2.png)

The same process is repeated with sentiment analysis that uses each individual attribute as a
reference, i.e. each review is scored on each of the 5 attributes using VADER sentiment analysis.
At this point, we have similarity scores as well as the attribute scores for each brand. The
average of each brand’s attribute scores is calculated and stored as `avg_score`.

![My Image](/images/Picture3.png)


Lastly, the final evaluation metric `evaluation_metric` is calculated by taking the average of the
`similarity_score` and `avg_score` for each brand. In order to produce the top
recommendations, we sort by the highest `evaluation_metric`.
**Cosign Similarity Scores:**

![My Image](/images/Picture4.png)

# Evaluating Cosine Similarity Calculations Against SpaCy Cosine Similarity Scores

As above, similarity scores are calculated between the attributes and brand reviews, however
this time we use the SpaCy library instead of the `get_cosine()` function defined earlier. The
scores do deviate a bit, yet the final brand recommendations come out to be the same, just in a
slightly different order.
**SpaCy Scores:**

![My Image](/images/Picture5.png)

**Group Members** : Domitille Chambon, Sam D'Avila, Steven Hobson, Saiansh Raizada, Johann
Thomas, & Purva Tiwari


