# DS_client-server_RMI_multithreaded
Short Description
Simplified view of the distributed Bingo game

Full Description
The system  will consists of 2 server processes (Bingo and
Winner server) and will support many player (client) processes using
Java RMI technology for entity communication.
A player through a GUI after authenticating to the system can:
▪ request a ticket (5X5) from the Bingo server
▪ be informed and received by the Bingo server about the drawing of a new number. This process can be implemented more efficiently using calls
callback
▪ to inform the Bingo server that he has played Bingo and receive a relevant response
if this was accepted
▪ to ask the Winner server who the Bingo winners are so far
▪ to inform the Bingo server that he is leaving the game

The first Bingo server simultaneously accepts connections from the various
players and is responsible for their authentication. Before their authentication
players must be allowed to join the server for the current
game but also for future use. Consider that two players cannot have the
same login details. He is also responsible for creating the sheets (5X5) for the players and filling them
with the random numbers.
Every time a player claims to have played Bingo, the server will have to check
if applicable or not and to inform the Winner server accordingly.
The second server (Winner server), when it receives a query for those so far
winners, finds the answer based on (use related file
objects), and sends it through the Bingo server to the customers. As long as he receives any
Bingo winner from the Bingo server, records it in the file.

However, in the event that there is a request for the registration of a winner at the same time
questions about the winners so far, a competitive condition is created, as the
base state will not be consistent across different executions of the application. In one
such case, the second server should prevent the execution of all the
other requests at that time and prioritize Bingo
server to do the registration
