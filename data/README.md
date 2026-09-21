# Dataset

This project uses the **Amazon Fine Food Reviews** dataset for sentiment analysis.

## Dataset Overview

The original dataset contains **568,454 customer reviews** and includes information such as:

- Product ID
- User ID
- Review score
- Review summary
- Review text
- Helpfulness information
- Review timestamp

## Dataset Usage

The complete CSV dataset is not included in this repository because of its large file size.

To reproduce the analysis:

1. Obtain the Amazon Fine Food Reviews dataset.
2. Rename the CSV file, if necessary, to:

   `AmazonFoodReviews.csv`

3. Place the file inside this directory:

   `data/AmazonFoodReviews.csv`

The expected project structure is:

    amazon-reviews-sentiment-analysis/
    ├── Amazon_Reviews_Sentiment_Analysis.ipynb
    ├── README.md
    ├── requirements.txt
    └── data/
        ├── README.md
        └── AmazonFoodReviews.csv

## Sentiment Labeling

For this project, review ratings are converted into sentiment labels:

| Rating | Sentiment |
|---|---|
| 1–2 Stars | Negative |
| 3 Stars | Excluded |
| 4–5 Stars | Positive |

Three-star reviews are excluded to create a binary sentiment classification problem.

## Note

The dataset is used only as the input data for this project and is intentionally excluded from version control.
