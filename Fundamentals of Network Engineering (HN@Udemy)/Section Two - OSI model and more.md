Here is what I have learned at second section in [HN Networking Course](https://www.udemy.com/course/fundamentals-of-networking-for-effective-backend-design/?couponCode=KEEPLEARNINGOCTB) 


> Seprate workloads between client and server
  
  It is a core fundemetal of todays' networks that we break our app into two sides 'Client' and 'Server'... but why? because we want to balance the workload , your poor phone cannot handle the high workloads (like complex queires or any sort of heavy load) so they came up with this idea make the server handle the heavy stuff while client do lightwight, and make both connect with each other through any kind of RPCs (wires, network(s),....)

> Communication Standardization Between Client and Server... but why ?
  - To get rid of network medium customization overhead for your app, for example without standard you need to make you own way or even freestyle to communicate through different mediums such as wires ethernet, wifi.
  - Upgrading network equipment without any burdens ... have a wifi today, then have an ethernet tomorrow.
  - App stablility throughout different mediums.


> Standard OSI Communication model
  I am not gonna identify each layer of 7 layers and its roles, but lets take a deep dive into a 'POST' request example that disccussed what happens from the POV of OSI mode when you do a POST request :
  - 7 : APPLICATION => You send the the request with JSON data to HTTPS Server = you hit 'SEND' at Postman
  - 6 : PRESENTATION => Serialize JSON to bytes
  - 5 : SESSION => Establish and manage 'session' between apps of the two hosts.
  - 4 : TRANSPORT => Sends 'SYN' to target port ('SYN' = "Hello can we have a connection?", it is the first step of 'Handshaking') 
  - 3 : NETWORK => Put 'SYN' in IP Pakcet and adds src/dst IPs to it.
  - 2 : DATA LINK =>  Put Packet into a Frame and adds src/dst MACs to it.
  - 1 : PHYSICAL => Transform into bits stream

  the other host will do the inverse of all of this operation but it will start from layer 1 up to layer 7.



> Switches , routers and more
  - Switches : connects different devices together, most of switches access the layer 2 frames to do its job.
  - Router : connects different networs (LAN, WAN, ...), need to access layer 3 packets.
  - Proxy, Firewall access layer 4 to see the dst port and block the request or manage in the prxy case.
  - Load Balancer/ CDN : needs to access layer 7 because it has some sort of app logic, for example if use traefik you need to make some configurations (or program you gateway app).


  

