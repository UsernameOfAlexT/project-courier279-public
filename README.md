# Courier279 Proposal

## A secure end-to-end encrypted messaging and sharing app with an immersive 3-D UI

### Team:
- Alexander Tam
- Tony Wu

### What is Courier279?

A secure and trustless messaging and sharing application that respects the privacy of its users.
- End-to-end encryption for direct messages, group messages, and files
- Files will utilize seperated-header encryption, allowing quick and flexible sharing by re-encryption of headers
- Trustless key management will ensure the server never has access to the private data of its users
- Create and manage contacts, and configure sharing permissions among contacts

Courier279 offers a unique 3-D user expirence:
- Centers on an immersive first-person 3-D operating environment
- Interactions such as viewing messages, contacts, incoming files, etc. will be done in this 3-D environment
- Customize your own operating environment with flexible tools, and visit other users' customized environments

### Beta Features

- 3D UI used for secure messaging between users

- Contact list to manage communications with other users

### Final Features

- Secure file sharing with flexible permissions

- Manage group chats and sharing

- Customize your own personal environment

- Visit other users in their environment; movements update in real time.

### Technologies

- Heavy frontend use of the *TweetNaCL* crypto library for end-to-end encryption
  - NaCL box format (ECDH) for direct messages
  - NaCL secretbox format (shared secret key) for group messages, files

- Trustless end-to-end encryption and key management
  - Client-generated EC keypairs, encrypted with Scrypt digest of user password
  - Independent hash sent for server authenication
  - Client-based seperate-header encryption for flexible file sharing

- Frontend use of *React* to manage client state, server communication, and the main 3-D UI

- The UI centers around a 3-D *three.js* canvas to provide an unique user expirence

- Backend composed of an *Express* server with a *MySQL* database for data storage

- Automated deployment via Docker

### Challenges expected

- Performance is expected to be an issue. There is much work to be performed on the client side between cryptographic work and 3-D rendering. Balancing responsiveness with having a full-featured application may take time.

- TweetNaCl and three.js are libraries the team will have to learn independently. There is some familiarity with the structure of both libraries already, but there will still be a learning curve.

- Race conditions and synchronization may be an issue once we begin attempting to handle sharing between multiple users

- A 3-D First-Person UI will be attractive, but likely difficult to work with and test on. It is expected that there will be many issues related to user interaction in the environment.

- Truly ensuring secrecy and security in the setup we've created may be an issue, especially when it comes to enforcing secrecy with multiple users
