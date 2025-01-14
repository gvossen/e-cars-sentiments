# e_cars_sentiments

`e_cars_sentiments` is a Python package designed to analyze sentiments related to electric cars. It leverages text mining techniques to perform sentiment analysis on data scraped from online sources, such as news articles, blogs, and forums. The package supports multiple languages, including English, German, Chinese, and Norwegian.

## Features

- **Data Scraping**: Collect text data from public websites and online sources using a URL or a list of URLs specified in a configuration file.
- **Text Preprocessing**: Clean and preprocess text data using Jieba for Chinese text segmentation and NLTK for stopword removal and tokenization.
- **Sentiment Analysis**: Analyze text for sentiments related to electric cars, identifying positive, negative, and neutral factors.
- **Visualization**: Generate visualizations, including pie charts, to represent sentiment analysis results.
- **Multilingual Support**: Analyze sentiment in multiple languages, including English, German, Chinese, and Norwegian.

## Installation

To install this package, clone the repository and install the dependencies using `pip`:

```bash
git clone https://github.com/yourusername/e_cars_sentiments.git
cd e_cars_sentiments
pip install -r requirements.txt
```

## Usage

### Running the Sentiment Analysis

You can run the sentiment analysis by specifying the mode (`url` or `file`) and the language code (`EN`, `DE`, `CN`, or `NO`) as command-line arguments.

#### Example Usage:

**URL Mode (German):**

```bash
python -m executor.executor --mode=url --language=DE
```
### File Mode (English):

```bash
python -m executor.executor --mode=file --language=EN
```

### Command-Line Arguments

- `--mode`: Specify the mode of data input. Use `url` to scrape data from the web or `file` to analyze text from a local file.
- `--language`: Specify the language code (`EN`, `DE`, `CN`, `NO`) for the sentiment analysis.

### Data Sources

For URL mode, the program will scrape data from a list of URLs specified in the `config.ini` file for the selected language. This file contains positive, negative, and neutral keywords, along with URLs to public online sources for each language.

## Challenges

### Data Collection

- **Unauthenticated Crawling**: Scraping data from seed URLs may result in too many requests and 429 errors. It’s recommended to implement rate limiting or save the scraped text in files for offline analysis.
- **Keyword Identification**: Identifying positive, negative, and neutral words in multiple languages can be challenging. The list of keywords has been limited to 200 words per sentiment to improve performance.
- **Review Data**: Collecting reviews from sources like Yelp or Google requires saving them in text files for processing due to potential scraping limitations.
- **Survey Data**: Processing survey data can be done using a weighted scoring system and representing it as a matrix (0,1) with respondents and possible answers. These can then be compared for sentiment trends.

### Data Analysis

- **Predicting E-Car Adoption/Sales**: Identify key variables that affect electric car adoption and sales. Neural networks, such as LSTM and BiLSTM, can be used for prediction.

- **Comparative Sentiment Analysis**: To compare sentiments across different regions (Norway, Germany, EU), deep learning models like LSTM and transformer-based models like BERT can be utilized. These models capture the sequence and context of text, helping to identify key deciding factors by analyzing sentiment patterns and focusing on important text elements.

    - [How multilingual is Multilingual BERT?](https://arxiv.org/pdf/1906.01502)
    - [Utilizing BERT for Aspect-Based Sentiment Analysis via Constructing Auxiliary Sentence](https://arxiv.org/abs/1903.09588)
    - [Understanding BERT - Key to Advanced Language Models](https://www.linkedin.com/pulse/understanding-bert-key-advanced-language-models-m-shivanandhan-f6jtc/)
    - [Building an LLM from Scratch (Sebastian Raschka)](https://sebastianraschka.com/)

## Future Work

- Implementing more sophisticated crawling mechanisms with authentication.
- Enhancing the sentiment analysis with more languages and dialects.
- Building and training neural networks for predictive analytics in electric car adoption and market trends.


