# blockchain-hw
# Running a Proof of Authority Blockchain

#  softwares installation
1. My crypto https://download.mycrypto.com/
2. Gitbash for windows users https://git-scm.com/downloads
3. Geth and tools v 1.9.7 https://geth.ethereum.org/downloads/


# To create mycrypto account 
Once you complete all those installation create an account on mycrypto.
choose `create New Wallet` in your right hand side.  
click `Generate a new wallet`.
Select `Mnemonic Phrase` and click on a `Generate a Mnemonic Phrase`.
Once it's generated type all those words into a seperate notebook, because you will need these to login your account.
After that, click `View & Send` and select `Mnemonic Phrase`.
Type all those words which you have written in your seperarate notebook to login your account.
When you login select the first crypto address.
In the right hand side you will be able to see your crypto address.
Congratulations! you have successfully created a mycrypto account. 


# Steps to create a blockchain
Once you download the geth and tools you will see `geth-alltools-darwin-amd64-1.9.7-a718daa6.tar.gz` in OS X, and a file called `geth-alltools-windows-amd64-1.9.7-a718daa6.zip` in Windows in your downloads folder.
Extract the geth and tools and paste the folder in the current directory mostly in your desktop.
Rename that folder hoewver you like e.g blockchain-tools.
open gitbash navigate to `blockchain-tools` folder.
type ./puppeth command in your terminal.
Name your network e.g homework2.
choose `Configure new genesis` by typing 2.    
choose `create new genesis from scratch` by typing 1.
choose `Ethash - proof-of-work` by typing 1.
It will ask you to paste your crypto address and then press enter.
press enter again to deny pre-funded with 1 wei.
Specify your chain id, type a chainid which you can remember easily for example 123.

# Creating two nodes accounts
create a node1 account
./geth account new --datadir node1 
Create a password which you can remember.
 you will see public address key and path of the secret key file copy that and paste into a  notebook and save it where you can easily acess it.
./geth account new --datadir node2 
create a password again which you can remember. password can be same it's not a problem.
you will see the same thing after creating node2 account. 
copy and paste public address key and path of the secret key file into a notebook where you have saved your node1 public address and path of the secret key file.
After that you have to create some json files in your blockchain-tools folder.
To export json file type
./geth init homework2.json --datadir node1 (this is my network name, you have to put your's)
you will see the message in your terminal `successfully wrote genesis state` repeat the same process for node2.
./geth init homework2.json --datadir node2
you will see the same message in your terminal `successfully wrote genesis state`


# To run nodes
Now we have to run nodes to check if our blockchain is mining or not.
Type this command in your terminal to run node1
./geth --datadir node1 --mine --minerthreads 1 --rpc --ipcdisable --allow-insecure-unlock --unlock "your node1 public address"
When you will run that command you will see the p2p address in your gitbash copy that and paste into that notebook where you have saved your node1 and node2 public address.
To run node2
./geth --datadir node2 --port 30304 --bootnodes "enode://node1 p2p address" --ipcdisable --allow-insecure-unlock --unlock "node2 public address"
While it's running you should see `Looking for peers` then `commit new mining work` and then `Blockchain sealed new network`

Note: When you will run node1 and node2 commands make sure you put your password quickly.

Go to mycrypto click `change network` you will see the `add custom node` option select that option.
Type your network name in the `node name` which you have created for example homework2.
In the dropdown menu select `custom option`.
Type your network name in the `network name` for exammple homework2.
In the url option, type http://127.0.0.1:8545 and save & use custom node.

# Let's Check it
Open my crypto you will see 0ETH and then goto `view & send`.
Select `Keystore file`.
select a `Blockchain-tools` folder.
Go to node1 folder select keystore and open that file.
Put your password and you will start to see some ETH in your crypto account.

Congradulations! You have created your own Blockchain.


