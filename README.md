# Email Textalyzer Prototype

## Getting Started
1. Pull this repo down and from the directory run `jupyter notebook`
2. Set up a google developer account and add a project to your account
3. Get your `credentials.json` file from google and stick it in this directory. It should look something like this
  ```
  {
    "installed": {
        "client_id": "<some number>.apps.googleusercontent.com",
        "project_id": "<your app name>-<some other number>",
        "auth_uri": "https://accounts.google.com/o/oauth2/auth",
        "token_uri": "https://oauth2.googleapis.com/token",
        "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
        "client_secret": "<some client secret>",
        "redirect_uris": ["urn:ietf:wg:oauth:2.0:oob","http://localhost"]
    }
  }
  ```
4. Open gmail and mark all the messages (well the first 50) as unread
5. Run the cells in order to create a randomly labeled corpus
6. You can fix the labels according to how you used them (I haven't gotten around to a nice UX mechanism for this yet) 
  * 0 for ignored 
  * 1 for you read it and it was important
  * 2 for it was so important you replied or downloaded attachments
7. Fit the `tf-idf vectorizer` and create the train/test split
8. Fit the models and see how they do (I just print the F1 score, good enough for hackathon right?)
9. Pick your favorite model and add it to the last cell and call `predict` on it when you get a new message and see how well you did.

## Notes + FAQ

Q1. Hey man, this sucks!
A1. I know right? Try giving it more/better data. NLP is one of those areas thats hard to get right in a weekend of drinking and learning python

Q2. You know there are libraries that do the pre-processing for you right?
A2. Yep, but the point of this exercise was to challenge myself, and get more control over how I analyze the text data so I can try different things. Anyone can throw together a thing in 3 lines of python because a tutorial told you how, but I didn't want to be yet another one of those.

Q3. Would this work for outlook?
A4. Sure, if you write an adapter for it. I dont use outlook so I have no idea what the response format for their email api looks like, but I don't imagine it being too hard.