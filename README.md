Application Flow
1. Sign Up / Log In
Users can sign up by providing a username and password. The system will store their data securely in the database.
Once registered, users can log in using their username and password.
After successful login, a JWT token is issued to maintain authentication.
2. Collapsible Left Menu (User List)
On the left side of the chat window, there will be a collapsible menu that displays all registered users.
The user can click on any other user’s name to initiate a private chat.
3. Chat Interface
After selecting a user, a chat window will open showing previous messages (if any) between the users.
The user can send a new message, which will be sent in real-time to the other user.
The chat window supports real-time updates using WebSockets, so new messages appear instantly.
4. Storing Messages
All messages between users are stored in the MongoDB database under a messages collection. Each message includes:
Sender ID
Receiver ID
Message content
Timestamp
5. Real-Time Messaging with WebSocket
When a message is sent, the backend (Node.js with Socket.io) broadcasts it to the recipient.
The WebSocket connection ensures that users can see the message as soon as it is sent without needing to refresh the page.
6. Retrieving Message History
When the chat window is opened, all previous messages between the selected users are retrieved from the database and displayed in the chat interface.
