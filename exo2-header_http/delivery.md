# 🕵️ Challenge 2 — HTTP Headers

I opened the capture introduction_headers.pcapng in Wireshark and applied the 'HTTP' filter:

Then I looked for HTTP requests that contain an Authorization header.
I found the following request :

POST /signout HTTP/1.1
Host: 127.0.0.1:5000
Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=

The string after Basic (dXNlcm5hbWU6cGFzc3dvcmQ=) is base64 encoded.
I decoded it using :

echo "dXNlcm5hbWU6cGFzc3dvcmQ=" | base64 --decode

This gave me the credentials in the format username:password.

Result

username:password

The server responded:

HTTP/1.0 200 OK
{
  "result": "signout successful"
}

Therefore, the user successfully signed out using HTTP Basic Authentication.
