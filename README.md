# Kaggle_Two-Sigma-Connect_Rental-Listing-Inquiries
Two Sigma Connect: Rental Listing Inquiries ( https://www.kaggle.com/c/two-sigma-connect-rental-listing-inquiries )


## Description
Finding the perfect place to call your new home should be more than browsing through endless listings. RentHop makes apartment search smarter by using data to sort rental listings by quality. But while looking for the perfect apartment is difficult enough, structuring and making sense of all available real estate data programmatically is even harder. Two Sigma and RentHop, a portfolio company of Two Sigma Ventures, invite Kagglers to unleash their creative engines to uncover business value in this unique recruiting competition.

![icon](https://kaggle2.blob.core.windows.net/competitions/kaggle/5590/media/twosigma-renthop-banner-250x250.png)


Two Sigma invites you to apply your talents in this recruiting competition featuring rental listing data from RentHop. Kagglers will predict the number of inquiries a new listing receives based on the listing’s creation date and other features. Doing so will help RentHop better handle fraud control, identify potential listing quality issues, and allow owners and agents to better understand renters’ needs and preferences.

Two Sigma has been at the forefront of applying technology and data science to financial forecasts. While their pioneering advances in big data, AI, and machine learning in the financial world have been pushing the industry forward, as with all other scientific progress, they are driven to make continual progress. This challenge is an opportunity for competitors to gain a sneak peek into Two Sigma's data science work outside of finance.

## Acknowledgments

This competition is co-hosted by Two Sigma and RentHop (a portfolio company of Two Sigma Ventures, which is a division of Two Sigma Investments) to encourage creativity in using real world data to solve everyday problems. 

![icon2](https://kaggle2.blob.core.windows.net/competitions/kaggle/5590/media/twosigma-renthop-banner-250x250.png)

## Evaluation
Submissions are evaluated using the [multi-class logarithmic loss](https://www.kaggle.com/wiki/MultiClassLogLoss). Each listing has one true class. For each listing, you must submit a set of predicted probabilities (one for every listing). The formula is then,

logloss=−1N∑i=1N∑j=1Myijlog⁡(pij),

where N is the number of listings in the test set, M is the number of class labels (3 classes),  log is the natural logarithm, yij is 1 if observation i belongs to class j and 0 otherwise, and pij is the predicted probability that observation i belongs to class j.

The submitted probabilities for a given listing are not required to sum to one because they are rescaled prior to being scored (each row is divided by the row sum). In order to avoid the extremes of the log function, predicted probabilities are replaced with max(min(p,1−10−15),10−15).


## Submission File

You must submit a csv file with the listing_id, and a probability for each class.

The order of the rows does not matter. The file must have a header and should look like the following:

## Data

In this competition, you will predict how popular an apartment rental listing is based on the listing content like text description, photos, number of bedrooms, price, etc. The data comes from renthop.com, an apartment listing website. These apartments are located in New York City.

The target variable, interest_level, is defined by the number of inquiries a listing has in the duration that the listing was live on the site. 

#### File descriptions

- train.json - the training set
- test.json - the test set
- sample_submission.csv - a sample submission file in the correct format
- images_sample.zip - listing images organized by listing_id (a sample of 100 listings)
- Kaggle-renthop.7z - (optional) listing images organized by listing_id. Total size: 78.5GB compressed. Distributed by BitTorrent (Kaggle-renthop.torrent). 

#### Data fields

- bathrooms: number of bathrooms
- bedrooms: number of bathrooms
- building_id
- created
- description
- display_address
- features: a list of features about this apartment
- latitude
- listing_id
- longitude
- manager_id
- photos: a list of photo links. You are welcome to download the pictures yourselves from renthop's site, but they are the same as imgs.zip. 
- price: in USD
- street_address
- interest_level: this is the target variable. It has 3 categories: 'high', 'medium', 'low'