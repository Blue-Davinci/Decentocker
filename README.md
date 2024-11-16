# Decentocker
<p align="center">
  <a href="" rel="noopener">
    <img width="300px" height="190px" src="https://i.ibb.co/1ZwW8jF/decentoker-modified.png" alt="Decentocker Project logo" style="border-radius:15px;">
  </a>
</p>

# Overview
decentocker is a decentralized poker game server built using Go (Golang). It allows players to connect to each other and play poker games in a peer-to-peer (P2P) manner. The server uses the TCP protocol for communication between players and provides an API for managing game states and player actions.

# Features
Decentralized architecture: Players connect directly to each other, eliminating the need for a central server.
+ P2P communication: Players communicate with each other using TCP connections, ensuring secure and reliable communication.
+ Game variants: The server supports various poker game variants, such as Texas Hold'em.
+ API: The server provides an API for managing game states and player actions, allowing for easy integration with front-end applications.


# Getting Started
To get started with decentocker, follow these steps:


+ Clone the repository:
`git clone https://github.com/blue-davinci/decentocker.git`

+ Install dependencies:
`go get -v -u github.com/blue-davinci/decentocker/...`

+ Build the server:
`go build -v -o decentocker main.go`

+ Run the server:
`./decentocker`

+ Start a new game by creating instances of the server and connecting them:
  ```
     playerA := makeServerAndStart(":3000", ":3001") // dealer
     playerB := makeServerAndStart(":4000", ":4001") // sb
     playerC := makeServerAndStart(":5000", ":5001") // bb
     playerD := makeServerAndStart(":7000", ":7001") // bb + 2

     playerB.Connect(playerA.ListenAddr)
     playerC.Connect(playerB.ListenAddr)
     playerD.Connect(playerC.ListenAddr)
```
