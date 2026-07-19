# Search Engine

A university coursework project (Information Retrieval course, 2022) implementing
the core pieces of a basic search engine from scratch.

## What it does

- **Crawler**: a small `crawler` class that fetches pages with `requests`, extracts
  `<a href>` links to keep crawling, and pulls `<p>` paragraph text into a CSV
  (`dataset.csv`).
- **Text cleaning**: strips HTML/punctuation and removes stopwords with NLTK.
- **Indexing & retrieval**: builds an inverted index over the cleaned documents and
  supports boolean `AND` / `OR` queries, plus a simple parser (`dynamic_query`) for
  mixed `and`/`or`/`not` queries.
- **Vectorization**: also builds a TF-IDF matrix of the corpus with scikit-learn's
  `TfidfVectorizer`.
- **Word similarity**: uses WordNet (via NLTK) to compute path similarity between
  word senses, e.g. how related "dog" and "cat" are.

`dataset.csv` in this repo is a sample of crawled/cleaned output from an earlier run.

## Tech stack

- Python
- requests, BeautifulSoup
- NLTK (stopwords, tokenizer, WordNet)
- scikit-learn (`TfidfVectorizer`)
- pandas, NumPy

## Running it

Open `IRS-FINAL.ipynb` in Jupyter and run the cells in order. The crawler cells make
live HTTP requests to an external site, so they need network access and may behave
differently if that site has changed.
