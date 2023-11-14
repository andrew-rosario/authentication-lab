Questions

Question 1: What authentication scheme is used by default in Django Rest Framework's browsable API? How is this managed?

Session, since Django uses its own backend login process over the HTTP standard/default login prompt in Basic. It is managed by making new administrators on the server.

Question 2: What authentication scheme is used by httpie when querying with the -a or --auth option flag?

HTTP Basic.

Question 3: What is the difference between Session Authentication and Token Authentication? How is Token Authentication an improvement over Basic Authentication?

Session Authentication is managed by the administrators of the server, where the server itself keeps track of logged in users by means of "sessions". "Sessions" are kept active until it expires, the administrators reject the session, or the user logs out or changes how it appears to the server. Token Authentication foregoes the use of a username and password and requires clients to send a token with every request. This token is unique to a specific user existing on the server, and often has a time limit or number of usages associated before it cannot be used anymore.

Token Authentication is an improvement over HTTP Basic for the following reasons:
- Tokens allow selective access to certain features of a API, versus entire access to a user's admin/user privileges.
- If a token was shared or exposed, then it doesn't affect the entire server, but only what the token had access to.
- Tokens can be deleted or regenerated without affecting the entire associated user account.



Question 4: Provide a high level summary of what happens during an OAuth2 authentication flow. For instance: bitbucket.org > Log In > Log in with Google. What happens when I click "Log in with Google"?

When the user clicks "Log In With Google", the user is giving permission for BitBucket to get user information from Google on their behalf. Next, the user's web browser is sent to Google's own authorization service (that is, their login page), and the user inputs their Google credentials.

Once Google has verified the credentials are correct, they return a access token to the user's web browser which is then given to BitBucket. The token thus gives access to the account on BitBucket associated with that account.

Question 5: Please provide a link to your code.

