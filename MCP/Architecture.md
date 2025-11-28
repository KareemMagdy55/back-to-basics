### Prerequisites
- Client-Server architecture: a distributed architecture where clients request services and servers provide them.
- JSON RPC: a stateless, lightweight remote procedure call (RPC) protocol that uses JSON (JavaScript Object Notation) as its data format.
- HTTP : protocol to transfer data (like webpages) between client and server, also it has verbs or methods (like POST for storing data) to specify action client wants.

---
- MCP follows a client-server architecture with the following components:
    - MCP Host   : AI App manges multiple MCP Clients.
    - MCP Client : The component that connects Host and Server by providing context to the Host. (Like HttpClient in C#)
    - MCP Server : A program that provides context to MCP clients.
 
- MCP Host   1 : N MCP Clients
- MCP Client 1 : 1 MCP Servers

- MCP Servers can execute locally or remotly.
---
MCP Layers 
 - Data Layer (inner layer) 
