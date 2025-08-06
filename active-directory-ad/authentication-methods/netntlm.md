# NetNTLM

NetNTLM works using a challenge-response mechanism. The following is the overview of the steps taken in the authentication process:

1. The client sends an authentication request to the desired server&#x20;
2. The server generates a random number and sends it as a challenge to the client
3. The client will combine their NTLM password hash with the challenge (along with other known data) to generate a response, which will be sent back to the server for verification
   * The response does not contain the client's NTLM password (or hash), but rather, it is used in computing the response instead
4. The server will forward the challenge and the response from the user to the Domain Controller for verification
5. The Domain Controller will use the challenge to re-calculate the response, and compare it to the response sent by the client. If it matches, the client is authenticated, else, access is denied
6. The authentication result is sent back to the server, before being forwarded to the client

&#x20;
