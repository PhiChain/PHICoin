# PHICoin: A Cryptocurrency to Learn about Cryptocurrencies

PHICoin is a fork of a fork of LiteCoin  (the second fork is called SmallChange). It was created for educational purposes with two main objectives in mind. First, we want to tell the story about cryptocurrencies in a learning-by-doing fashiong; and second, we want to help people to create their own cryptocurrency, i.e. with the features they would like to consider within the boundaries of the Litecoin setup, e.g. Proof-of-Work, etc.  

We don't take any credit for the develop of the coding, outside the few changes we made. All credit goes to the creator of LiteCoin and SmallChange.


## References
`LearnCoin`
`SmallChange`
`Litecoin`

## Usage - Development process

### Preparing my development environment

For you can work with PHICoin is necessary that you install the next libraries over Ubuntu 14 -Linux.

```julia
$ sudo apt-get install git
$ sudo apt-get install libboost-dev
$ sudo apt-get install libboost-system-dev
$ sudo apt-get install libboost-program-options-dev
$ sudo apt-get install libboost-thread-dev
$ sudo apt-get install libboost-filesystem-dev
$ sudo apt-get install libcurl4-openssl-dev
$ sudo apt-get install libdb5.1-dev
$ sudo apt-get install libdb5.1++-dev
$ sudo apt-get install qt-sdk
$ sudo apt-get install libminiupnpc-dev
$ sudo apt-get install build-essential
$ sudo apt-get install openssl
```

Since it is necessary to have two machines running in a common network, we will use virtual machines in a VMWare environment (of course you can use any other alternative to emulate operating systems). To download vmware you can use the following links:
- for [Linux][Linux]
- for [Windows][Windows]
- for [Mac][Mac]

The operating system with all the required libraries (previously listed) is available at Mega - [Ubuntu 14][Ubuntu 14]. After downloading,  create a copy of the file and install two machines in VMWare (each one started from a different file). 

### Cloning PHICoin
On each virtual machine, open the terminal and download the project.
```julia
$ git clone https://github.com/franciscorosales-marticorena/PHICoin.git
```

### Installing PHICoin
In the project, enter `.../PHICoin/src` in a terminal window and execute:
```julia
$ make -f makefile.unix	// creates wallet
$ ./PHICoin	// asks for a user and a password
```
If evrything went well, you will see a message requesting a user and password for your PHICoin wallet

### Setting up our credentials
In the directory of your OS enter  `./PHICoin` and within this directory, create a file called `PHICoin.conf` that contains the following:
```julia
	rpcuser=<<unique_user>>
	rpcpassword=<<unique_password>>
	addnode=<<IP_of_the_other_computer>>
```

### Mining
This is the process by which the miners receive rewards, to start the mine in PHICoin return to `.../PHICoin/src` in the terminal and execute:
```julia
# First we need run our node:
$ ./PHICoin & // starts the service (you are already a node)
$ ./PHICoin getinfo // information about the node

# Now we can star the mining:
$ ./PHICoin setgenerate true 4 // start mining using multi-threads
$ ./PHICoin getmininginfo // information about the mining
$ ./PHICoin getbalance // check the account balance
```
Note: Mining is not necessary, but to run your node is necessary in every computer.

### Making transactions
After starting the mining we wait until we have some money to start our transactions.
```julia
# First we need create an account:
$ ./PHICoin getnewaddress "name_of_account"
$ ./PHICoin listaccounts

# Now we make our first transaction
$ ./PHICoin move "" "name_of_account" "amount"
$ ./PHICoin sendtoaddress "address_of_wallet" "amount"
$ ./PHICoin gettransaction "transaction_hash"
```
### Consulting the BlockChain
If I want to see the blocks and transactions, we can use:
```julia
$ ./PHICoin listsinceblock
$ ./PHICoin listtransactions
$ ./PHICoin listunspent
```

## Warning
PHICoin should not be used as a real cryptocurrency. All of the coin parameters are chosen arbitrarily or at most with 'fairness' towards everyone in mind. Again, this PHICoin exists becuse:
 -  proves that really anyone(!) can start a Litecoin/Bitcoin based currency (just look at the changes I applied to the original Litecoin source, for genesis block generation look at main.cpp)
 - allowed us to experiment with coin parameters (in a private network)

## keywords
`PHICoin`
`Cryptocurrency`


[Linux]:https://www.vmware.com/products/workstation-for-linux.html
[Windows]:https://www.vmware.com/products/workstation.html
[Mac]:https://www.vmware.com/products/fusion.html
[Ubuntu 14]:https://mega.nz/#!5vpFWCZS!lfyKNxBqTHriyihUsrMtVtPE2tX3CmhKTBMWnDJ0-bQ
