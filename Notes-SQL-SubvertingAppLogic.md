# Subverting Application Logic

- Consider an application that lets users log in with a username and password.
- If a user submits the username wiener and the password bluecheese, the application checks the credentials by performing the following SQL query:

`SELECT * FROM users WHERE username = 'wiener' AND password = 'bluecheese'`

- If the query returns the details of a user, then the login is successful. Otherwise, it is rejected.
