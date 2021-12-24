# cryptz-blockchain

The purpose of this repo is to demonstrate the setup of a private testnet network that uses **Proof of Authority** to allow for testing and exploration of the blockchain at ZBank.

Tools that will be used here are:
- Puppeth - to generate a genesis block
- GETH - a commandline tool to create keys, initialise nodes and connect nodes<br/><br/>

# Setting Up the Private POA Network

## Create Accounts

create the node directories: 
> mkdir node1 node2

<span style="color:red">*create new account for node1:*</span> 
>**$ ./geth --datadir node1/ account new**
<br/><span style="color:lightgreen">account 1 created:</span>  <span style="color:yellow">0x06d6FA1E86dC28DCbD49d22B0A3255b783A153B5</span>

![](./screenshots/sc001.jpg)
<img src="./screenshots/sc001.jpg"/>

<span style="color:red">*create new account for node2:*</span> 
>**$ ./geth --datadir node2/ account new**
<br>

<span style="color:lightgreen">account 2 created:</span>  <span style="color:yellow">0x96947332AB7ef0d231bCA8877F2e004a2BEb32d2</span>


![](./screenshots/sc002.jpg)
<br><br>

<hr/>

## Configure Genesis and the Network

![](./screenshots/sc003.jpg)

![](./screenshots/sc004.jpg)
![](./screenshots/sc005.jpg)
![](./screenshots/sc006.jpg)

<hr/>

## Initialise the Nodes

>./geth --datadir node1/ init cryptz.json <br/>
> ./geth --datadir node2/ init cryptz.json

![](./screenshots/sc007.jpg)


<hr/>

## Create a Boot Node
Boot node helps node discovery for network

>./bootnode -genkey boot.key <br/>
>./bootnode -nodekey boot.key -verbosity 9 -addr :30310

<i>enode://56762102f38a79c15bfabf80df53b60dba16b7773f9a7c24c68e358e8fb9ce5bc8ef8e2a79ceb91b2939a867262954f5f495006def87c9140a6480a8b00779d0@127.0.0.1:0?discport=30310</i>


![](./screenshots/sc008.jpg)
