# Data README

This dataset is constructed for paper "SPOTLENS: A Generic Framework for Discovering Public Perceptions from Social Media with a Case Study on Drones".

**The paper is under review. We have released data samples. The full _DroneSenti_ and the large drone corpus will be released upon paper publication.**


The whole corpus consists of 1 million online posts collected from X (formerly Twitter) and Reddit.
_DroneSenti_ is a manually annotated subset for sentiment classification. 



## Human-annotated _DroneSenti_ Dataset 

**_DroneSenti_** is a dataset constructed from online Twitter and Reddit discussions. 
Each post is annotated with one of the following sentiment labels: Positive, Negative, and Neutral. 

Data can be found under the `DroneSenti` folder.


### Data Format

The annotated data is organized in JSONL format. 
For X (formerly Twitter), each row corresponds to a single annotated post.
For Reddit, each row corresponds to a conversation that includes a list of annotated posts.

An annotated post includes the following data fields:
- `text`: Preprocessed post text
- `sentiment`: Gold sentiment label (positive/ negative/ neutral), determined by majority voting 
- `annotations`: Original annotations from three independent annotators


### Data Statistics

| data_source | total | positive | negative | neutral |
|-------------|-------|----------|----------|---------|
| reddit      | 500   | 86       | 109      | 305     |
| twitter     | 2501  | 207      | 405      | 1889    |
| total       | 3001  | 293      | 514      | 2194    |




## Large Drone Corpus

The complete drone corpus contains over 1 million posts from X (formerly Twitter) and Reddit platforms. 

For quick exploration, you can check some sample data in the `corpus` folder.

Due to X's data policy, we cannot re-distribute the Tweet text content. We provide the post IDs (`tweet_id`) so that end users can rehydrate the content with X API: [more info here](https://developer.x.com/en/developer-terms/more-on-restricted-use-cases#:~:text=Redistribution%20of%20X%20content,in%20a%20public%20Github%20repository)


### Data Format
Twitter Data (CSV format):
- `idx`: Sequential index
- `tweet_id`: Unique IDs that can be used to rehydrate the original content
- `timestamp`: Post creation time
- `sentiment`: Sentiment label (positive/ negative/ neutral) predicted by the fine-tuned LDR-TimeLM model

Reddit Data (JSONL format):
- `conv_id`: Unique conversation identifier generated during pre-processing
- `conversation`: List of posts in a Reddit conversational discussion, each containing:
  - `text`: Pre-processed post content
  - `author`: Author identifier within each conversation, anonymized
  - `timestamp`: Post creation time
  - `sentiment`: Sentiment label (positive/ negative/ neutral) predicted by the fine-tuned LDR-TimeLM model


### Data Statistics
The Twitter part includes a total of 774,822 tweets.
The Reddit part includes 55,617 discussion conversations that count to a total of 275,168 pre-processed posts.

More details will be released upon paper publication.

