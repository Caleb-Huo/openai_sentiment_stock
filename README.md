# openai sentiment analysis for stock
- Sentiment analysis of stock based on Reddit posts and comments
 
## Resources:
- openAI API basics:
  - https://caleb-huo.github.io/teaching/2023FALL/lectures/Week16_ChatGPT/chatGPT_basics.html

## How to use API call to connect to Reddit:  

To retrieve a post title from the "finance" subreddit using PRAW (Python Reddit API Wrapper), you can follow these steps:

1. Ceate a Reddit Account: If you don't already have one, sign up for a Reddit account.
2. Create a Reddit App:
  - Log in to Reddit and go to [the Reddit App page](https://www.reddit.com/prefs/apps).
  - Click on the “Create App” or “Create Another App” button at the bottom.
  - Fill out the form:
3. Get client_id and client_secret:
  - After creating the app, you'll be redirected to the app's page. The client_id is the string listed just under “personal use script”. The client_secret is the string listed next to “secret”.
4. Install PRAW:
  - If you haven't already installed PRAW, you can do so using pip:
```
Copy code
pip install praw
```
5. Set Up PRAW in Your Python Script:
Use the client_id, client_secret, and a user_agent to set up PRAW. Replace 'your_client_id', 'your_client_secret', and 'your_user_agent' with your actual credentials and a descriptive user agent.

```
import praw

reddit = praw.Reddit(client_id='your_client_id',
                     client_secret='your_client_secret',
                     user_agent='your_user_agent')
```
6. Acessing Reddit Data:
Now, you can use the reddit object to access various functionalities of the Reddit API, such as reading posts, comments, and other data from specific subreddits.
```
subreddit = reddit.subreddit("stocks")
for post in subreddit.new(limit=5):
  print("Title:", post.title)
  print("Main Text:", post.selftext)
```
