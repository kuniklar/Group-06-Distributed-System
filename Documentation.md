# Documentation

## Starting and shutting down the system



## Functions of the chat application:
1. Users can create an chat room / chat group
2. Users can join an existing chat room / chat group
4. User can send messages in an existing chat room / chat group
6. Users can leave an existing chat room / chat group

### Rules / Limitations:

   + A user can only be in one chat room / chat group at a time.
   + A chat room / chat group is closing when all users left.
   + 

## Scenarios:

1.Error Detection:

   + A (the lead) servers is down.
   + 


## Hard-requirements

1. Error Detection:

    + Heartbeats to monitor server availability.

2. Error Handling: 

    + Implementation of the LCR algorithm for electing a new leader server.

4. Use of mulitcast for efficient transmission of messages to mulitple recipients

## Methods
### Clients
1. Find server
2. handle_messages_from_server

### Server
1. handle_broadcast_server_requests
    + where_servers_find_each_other
3. lcr / bully
5. Heartbeat //via timestamp
6. handle_leader_update
    + After selecting a new leader it ensures of the shared information (list of clients when...leave or join a chatroom) - this method stops on the leader server (sender not an recipient)
7. detecting_missing_heartbeat_from_leader
8. handle_broadcast_client_requests
    + the leader-server answers the client with and provides its ip address 
10. handle_send_message_request
