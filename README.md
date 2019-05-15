# AI home assignment

## Background

Amazon wants to develop a feature that provides sellers quantitative insight for negative reviews. A tool will calculate the most often mentioned 3 reasons for bad review scores (2 or lower) for any given product

The products with reviews can be found [here](http://jmcauley.ucsd.edu/data/amazon/). Product information is tied to Amazon through the link `https://www.amazon.com/dp/<asin>` but integrating their API is not the scope of this project. We can assume that any request contains the product ID (`asin` in the dataset).

A review looks like this

```json
    {
      "asin": "0000013714",
      "reviewText": "I bought this for my husband who plays the piano.  He is having a wonderful time playing these old hymns.  The music  is at times hard to read because we think the book was published for singing from more than playing from.  Great purchase though!",
      "overall": 5.0,
      "summary": "Heavenly Highway Hymns"
    }
```

## Requirements

- Upon entering a product(id)/asin, it should return a textual representation of the negative reason that is most helpful and which percentage of bad reviews mention it. E.g.:

```json
    { "reason": "too expensive", "frequency": 0.23 }
```

- You should be able to show that the clustering by reason can handle multiple reasons in the same review and word/sentence variations.
- The solution should show a POC solution, for example in an Jupyter notebook or as a standalone script
- Performance is not important

## Submitting the solution

Easiest would be a Jupyter notebook on GitHub but that's not a hard requirement. A standalone application is also possible, just make sure that the repository contains a README on how to use the tool

## What we care about

- We're interested in a methodical approach. Failed attempts with lessons learned are as important as the end result
- This is not a one time script - don't write it that way. The solution would be integrated into a tool; readability counts!
- Explainability is important. How can we debug the solution? Can the tool show the strings used for clustering? Can we show the reviews with the shortest/largest distance to the cluster center? Or, if no clustering is used, how can we make sure that the common reasons are useful information?
- Visualisations can be the most efficient way to communicate the inner workings of your model. Use them where it makes sense
- It's not about using the most difficult approach or implementing the newest paper. Having something stable that could be used in a production setting is the top priority
