import streamlit as st
import pandas as pd
import plotly.express as px
import seaborn as sns
import matplotlib.pyplot as plt

# Streamlit App Title
st.title("Airline Tweets Sentiment Analysis")

# Load Data
url = 'https://raw.githubusercontent.com/shah-kavya/KS-tweets/refs/heads/main/Tweets.csv'
tweets = pd.read_csv(url)

st.subheader("Raw Data")
st.write(tweets.head())

# Sentiment Count Pie Chart
sentiment_counts = tweets['airline_sentiment'].value_counts().reset_index()
sentiment_counts.columns = ['sentiment', 'count']

st.subheader("Sentiment Count of Tweets")
fig_pie = px.pie(sentiment_counts, values='count', names='sentiment', title='Count of Tweets by Sentiment')
st.plotly_chart(fig_pie)

# Tweet Count by Airline (Bar Chart)
airline_counts = tweets['airline'].value_counts().reset_index()
airline_counts.columns = ['airline', 'count']

st.subheader("Tweet Count by Airlines")

fig, ax = plt.subplots(figsize=(10, 6))
sns.barplot(x='airline', y='count', hue='airline', palette='pastel', legend=False, data=airline_counts, ax=ax)

ax.set_xlabel('Airline')
ax.set_ylabel('Count')
ax.set_title('Tweet Counts by Airlines')
plt.xticks(rotation=45)

st.pyplot(fig)
