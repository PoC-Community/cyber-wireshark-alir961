# 🕵️ Challenge 3 — HTTPS

I opened the capture introduction_https.pcapng in Wireshark and applied the 'HTTP' filter:

I noticed that no HTTP requests or responses were readable.
This is because the traffic is actually HTTPS not HTTP and it's encrypted using TLS.

HTTPS encrypts the body and the headers (except some metadata like SNI in the ClientHello).

This ensures that credentials and other sensitive data are not visible on the network.

Even if the user sends a JSON with credentials in a POST request we cannot see it without decrypting the TLS traffic (which requires the server’s private key or session keys).

Result

The content of the POST request is unreadable because HTTPS encrypts the HTTP traffic.
This is why we cannot see the credentials in plain text in the capture.
