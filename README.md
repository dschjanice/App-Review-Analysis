# ReviewRevealer: App review analysis through sentiment analysis and topic modeling on the example of ChatGPT


This repository documents the data science project “ReviewRevealer” by [Janice Schönfeld](https://www.linkedin.com/in/janice-schönfeld/), [Andrii Ivanytskyi](https://www.linkedin.com/in/andrii-ivanytskyi-908364292/), and [Martje Buss](https://www.linkedin.com/in/martje-buss-104550217/?originalSubdomain=de) (last updated: 22.11.2023) from the SPICED Academy Data Science Bootcamp, cohort: riceregression. It includes all data, scripts, and visualizations that were used for the project presentation (LINK). There is a separate repository for the streamlit dashboard which can be found here:
If you have any questions, please contact: XXX

### The way to success:

Please work through all the notebooks in this particular order:

1. [Apple Store Scraper for ChatGPT Reviews](notebooks/0_review-scraper_apple.ipynb) / [Google Play Store Scraper for ChatGPT Reviews](notebooks/0_review-scraper_google.py)
2. [Data Cleaning and Preprocesing](notebooks/2_data_cleaning_combined.ipynb)
3. [Exploratory Data Analysis](notebooks/1_eda_combined.ipynb)
4. [Sentiment Analysis](notebooks/3_sentiment-reviewwise.ipynb)
5. [Topic Modeling](notebooks/4_bertopic_topic-modeling.ipynb)


- In the first notebook you see how the data was scraped using two different packages; one for the Google Play Store and the other one for the Apple Store.
- In the second notebook the data was cleaned according to those steps:
    1. Combining data frames & filter for English language
    2. Remove emojis and symbols
    3. Standardize mentions of ChatGPT & OpenAI
    4. Spell Checking
- In the third notebook a Exploratory Data Analysis was performed to obtain a generell overview on the data. 
- The fourth notebooks uses pretrained models for unsupervised sentiment classification to categorize the reviews.
- Finally, inside the fifth notebook a topic model was created using the BERTopic library.



## Environment

In some cases it is necessary to install the Rust compiler for the transformers library.

```BASH
brew install rustup
rustup-init
```
Than press ```1``` for the standard installation.

Then we can go on to install hdf5:

```BASH
 brew install hdf5
```
With the system setup like that, we can go and create our environment and install tensorflow

```BASH
pyenv local 3.11.3
python -m venv .venv
source .venv/bin/activate
export HDF5_DIR=/opt/homebrew/Cellar/hdf5/1.14.1

pip install -U pip
pip install --no-binary=h5py h5py
pip install -r requirements.txt
```
If you are working on Windows type the following commands in the PowerShell:

```sh
python -m venv .venv
.venv\Scripts\Activate.ps1
```

*Note: If there are errors during environment setup, try removing the versions from the failing packages in the requirements file.*