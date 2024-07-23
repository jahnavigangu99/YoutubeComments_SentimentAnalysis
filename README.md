# YouTube Comment Sentiment Analysis

## Objective

The primary objective of this project is to perform sentiment analysis on YouTube comments to gain insights into the public perception of video content. By classifying comments into positive, negative, and neutral sentiments, we aim to understand viewer reactions and derive meaningful patterns from the engagement data.

## Project Description

This project involves several key phases, each designed to build upon the previous to refine our data and extract valuable insights:

### Data Collection

YouTube comments data is collected using the YouTube API, which provides access to comments, their metadata, and associated video details. This data forms the foundation of our analysis.

### Data Preprocessing

The raw data undergoes a series of preprocessing steps to make it suitable for analysis. These steps include:
- Removing missing values from the 'Comment' column to ensure data quality.
- Parsing and converting 'Published At' timestamps into datetime objects for better time-series analysis.
- Extracting features like comment length and generating a cleaned version of the comments by removing URLs, special characters, and applying lemmatization to reduce noise in the text data.

### Feature Engineering

Additional features are derived to enhance the model's performance:
- Categorizing comment lengths into predefined bins (Very Short, Short, Medium, Long) to see the distribution of comment verbosity.
- Calculating the frequency of comments per author to identify highly active users.
- Implementing log transformations on 'Likes' to normalize the distribution and create a feature that captures engagement intensity relative to the comment's length.

### Sentiment Analysis

Sentiment scores are calculated for each cleaned comment using the TextBlob library, which provides a simple API to access common text processing operations and sentiment analysis. Comments are classified into three categories:
- Positive
- Neutral
- Negative

This sentiment data is then used to add sentiment-related features to our dataset.

### Model Development

A machine learning model (Random Forest Classifier) is trained using the features extracted in the previous steps. The model predicts the sentiment category based on the textual content of the comments and other derived features.

### Evaluation

The model is evaluated using accuracy and cross-validation scores to ensure its reliability and robustness. Additionally, classification reports provide detailed insight into the precision, recall, and F1-score for each sentiment category.

## Results

Initial results have shown high accuracy in classifying the sentiments of YouTube comments. The feature importance analysis revealed which variables most significantly impact the model's decision-making process, offering insights into how different aspects of the comments correlate with viewer sentiment.

## Usage

The code is structured to be reusable for different datasets or expanded to include more complex features. It can be adjusted to analyze comments from other social media platforms by modifying the data collection and preprocessing steps accordingly.

## Future Work

Future enhancements could include:
- Expanding the dataset to include more diverse video content for a broader analysis.
- Implementing more complex natural language processing techniques to improve the understanding of context within comments.
- Integrating the model into a real-time analytics tool for YouTube creators to get immediate feedback on viewer sentiment.

## Conclusion

This project demonstrates the power of machine learning and natural language processing in extracting meaningful insights from unstructured text data, providing a valuable tool for content creators to understand and engage with their audience effectively.

