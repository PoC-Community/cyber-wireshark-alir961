# 🕵️ Challenge 1 — Basic HTTP

I opened the capture in Wireshark and applied the 'HTTP' filter
Then I looked for HTTP requests sent by the client.
I selected the POST request and used :

Right-click → Follow → HTTP Stream

This allowed me to reconstruct the full communication between the client and the server.

From there I was able to view the JSON payload sent by the client as well as the server’s response.

Result

The user is attempting to log in by sending the following request :

POST /signin HTTP/1.1
Content-Type: application/json

{"username":"Groot", "password":"Je_sappelle_Groot"}

The server responds with:

HTTP/1.0 200 OK
{
  "error": "login or password does not match"
}

Therefore, the user is trying to authenticate but the login attempt fails due to invalid credentials.
