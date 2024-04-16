![Screenshot 2024-04-16 153648](https://github.com/SRISOWMITHRAPAWAN/Blazor_SignalR_wasm/assets/108918837/9bc06632-6363-4a78-bdcb-07f44cbcae98)
Overview
The implementation of real-time communication using SignalR in a chat application. SignalR enables bi-directional communication between clients and servers over various transport mechanisms.

Architecture
Client-Server Interaction:
Clients, represented by a Blazor application, communicate with the server using SignalR for real-time messaging.
The server, implemented as an Azure Function, handles incoming requests and broadcasts messages to connected clients.
Components
Client-Side (Blazor)

User Interface (UI):

Displays chat messages and input fields for sending messages.
Dynamically renders messages as sender or receiver based on the user's input.
Provides input fields for the user's name and message content.
Updates UI in real-time upon receiving messages from the server.
SignalR Hub Connection:

Initiates a SignalR hub connection with the server upon component initialization.
Handles incoming messages from the server and updates the UI accordingly.
Sends user messages to the server for broadcasting to other clients.
Server-Side (Azure Function)

HTTP Trigger Functions:

Expose endpoints to handle HTTP POST requests for message transmission and negotiation.
Receive incoming messages from clients and broadcast them to connected clients via SignalR.
SignalR Integration:

Utilizes SignalR bindings to interact with the SignalR service.
Sends messages to connected clients using IAsyncCollector<SignalRMessage>.
Workflow
Initialization:

Upon component initialization, the client establishes a SignalR connection with the server.
Message Transmission:

Users input their name and message in the UI.
When the "Send" button is clicked, the client sends the message to the server via an HTTP POST request to the /messages endpoint.
The server receives the message, processes it, and broadcasts it to all connected clients using SignalR.
Real-Time Updates:

Upon receiving a message from the server, the client updates the UI to display the new message in real-time.
SignalR Connection Status
The UI reflects the SignalR connection status to indicate whether the client is connected to the server.
The "Send" button is enabled/disabled based on the connection status, ensuring messages are sent only when the connection is established.
Conclusion
The implementation effectively demonstrates the integration of SignalR for real-time communication between clients and servers in a chat application. Users can exchange messages seamlessly, and the UI updates in real-time to reflect the ongoing conversation.


