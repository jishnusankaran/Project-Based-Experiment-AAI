<H3>ENTER YOUR NAME: JISHNUPRIYAN S</H3>
<H3>ENTER YOUR REGISTER NO.212223240061</H3>
<H3>DATE:</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
Perform sentiment analysis using your Facebook data and filter the data that has only Positive feedback for the code given in the following link.

## Program:
```
!pip install pandas textblob nltk

import pandas as pd
from textblob import TextBlob

# Sample DataFrame simulating Facebook data
data = {
    'post_id': [1, 2, 3, 4],
    'content': [
        'I love the new update!',
        'This is the worst experience ever.',
        'The app is okay, not great.',
        'Absolutely terrible support!'
    ]
}

# Create DataFrame
df = pd.DataFrame(data)

# Function to classify sentiment
def get_sentiment(text):
    analysis = TextBlob(text)
    # Classifying sentiment: < 0 indicates negative sentiment
    if analysis.sentiment.polarity < 0:
        return 'negative'
    else:
        return 'positive'

# Apply the sentiment analysis function to the content
df['sentiment'] = df['content'].apply(get_sentiment)

# Filter for negative feedback
negative_feedback = df[df['sentiment'] == 'negative']

# Display negative feedback
print("Negative Feedback:")
print(negative_feedback[['post_id', 'content']])

```
## Output:
![alt text](<Screenshot 2025-04-29 084725.png>)
## Inference:
Thus sentiment analysis using Facebook data is done and filtering the data that has only positive feedback for the code is executed successfully.
