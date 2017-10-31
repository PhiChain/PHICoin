# PHICoin: a educational cryptocurrency.

[![Build Status](https://travis-ci.org/ChrisRackauckas/ExamplePackage.jl.svg?branch=master)](https://travis-ci.org/ChrisRackauckas/ExamplePackage.jl)
[![Build status](https://ci.appveyor.com/api/projects/status/9iuvdt0j0mw6au0k?svg=true)](https://ci.appveyor.com/project/ChrisRackauckas/examplepackage-jl)

PHICoin is based off of LearnCoin and SmallChange, anothers cryptocurrencies which is itself based off of the original Litecoin source code. Users will be able to modify PHICoin into their own cryptocurrency. Ideally users should have at least two computers running Ubuntu 14 to begin, although other versions of Ubuntu or Linux distributions also work as well.
We don't take any credit for the Develop of codes, barring the few changes I have made. All credit goes to the creator of LearnCoin and others references.

## Details


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

Is necessary you have two machines run in a common network.

We will usage a virtual machine in VMWare, the proof version in here:
- for [Linux][Linux]
- for [Windows][Windows]
- for [Mac][Mac]

Then, download an Ubuntu 14 image from Mega - [Ubuntu 14][Ubuntu 14], create a copy and install both machines in VMWare, the user is `linux` and the password is `admin123`.
* Remember: VMWare is not necessary, I use it because it is versatile.


### Downloading PHICoin
On both computers, open the terminal in your favorite directory and download the project.
```julia
$ git clone https://github.com/franciscorosales-marticorena/PHICoin.git
```

### Installing PHICoin
In the project, enter `.../PHICoin/src` for the terminal and execute:
```julia
$ make -f makefile.unix	// Creas tu billetera en el directorio de tu SO
$ ./PHICoin	// Te solicitara un usuario y una contraseña
```
If you did well, you will see a message requesting a user and password for your PHICoin wallet

### Setting up our credentials
In the directory of your OS enter to `./PHICoin` and within this, we create a file called `PHICoin.conf` that will contain the following:
```julia
	rpcuser=<<usuario_unico>>
	rpcpassword=<<contrasenna_unica>>
	addnode=<<IP de tu otra computadora>>
```

### Mining
This is the process by which the miners receive rewards, to start the mine in PHICoin return to `.../PHICoin/src` by the terminal and execute:
```julia
# First we need run our node:
$ ./PHICoin & // Inicia el servicio (ya eres un nodo)
$ ./PHICoin getinfo // Informacion acerca de su nodo

# Now we can star the mining:
$ ./PHICoin setgenerate true 4 // Inicias a Minar usando multi-hilos
$ ./PHICoin getmininginfo // Informacion acerca del minado
$ ./PHICoin getbalance // Podemos ver cuanto dinero tenemos
```
•	The mining is not necessary, but run your node is necessary in every computer.

### Making transactions
After starting the mining we hope to have some money to start our transactions.
```julia
# First we need create an account:
$ ./PHICoin getnewaddress "tu_nombre_de_Cuenta"
$ ./PHICoin listaccounts

# Now we make our first transaction
$ ./PHICoin move "" "tu_nombre_de_cuenta" "monto"
$ ./PHICoin sendtoaddress "direccion_billetera" "monto"
$ ./PHICoin gettransaction "hash_de_tx"
```
### Consulting the BlockChain
If I want to see the blocks and transactions, we can use:
```julia
$ ./PHICoin listsinceblock
$ ./PHICoin listtransactions
$ ./PHICoin listunspent
```

## Note
For more information you write to: 

## keyword
`PHICoin`
`Cryptocurrency`


[Linux]:https://www.vmware.com/products/workstation-for-linux.html
[Windows]:https://www.vmware.com/products/workstation.html
[Mac]:https://www.vmware.com/products/fusion.html
[Ubuntu 14]:https://mega.nz/#!0TBUyaLD!3g65KW6DkIsS15vuWchMEaTT2Xomg_RstXZbSDjQKK4
