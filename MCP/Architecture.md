- Client-Server architecture: a distributed architecture where clients request services and servers provide them.

- MCP follows a client-server architecture with the following components:
    - MCP Host   : AI App manges multiple MCP Clients.
    - MCP Client : The component that connects Host and Server by providing context to the Host. (Like HttpClient in C#)
    - MCP Server : A program that provides context to MCP clients.
 
- MCP Host   1 : N MCP Clients
- MCP Client 1 : 1 MCP Servers

- MCP Servers can execute locally or remotly.

