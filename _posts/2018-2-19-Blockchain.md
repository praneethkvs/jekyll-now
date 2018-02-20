---
layout: post
title:  Setting up a Blockchain using MultiChain
---

### Overview
This is a tutorial that walks you through the process of spinning up a blockchain using the MultiChain software
which people can download and run to design, deploy, and operate distributed ledgers (blockchains) that track
ownership of digital tokens or assets.

### Initial Setup
#### Step:1  
The First thing we need to do is download the MultiChain software.
You can head on over to <https://www.multichain.com> and click "Download MultiChain" or 
click on the following link <https://www.multichain.com/download-install/>
which should directly take you to the download page as seen in the image below.  
  

![MultiChain Download Page]({{ site.baseurl }}/images/Download.PNG "MultiChain Download Page")

Select the correct version based on your operating system.   
**Note: There is no supported Mac version for MultiChain as of now.**

#### Step:2  
Extract the downloaded zip file into a directory. You should see the following files.
  
![MultiChain Folder]({{ site.baseurl }}/images/folder.PNG "MultiChain Folder")

#### Step:3
Open the extracted multichain folder then type in cmd into the address bar to open a command window. Note,
you should open the command window in the directory where MultiChain is stored or it won't work.

![MultiChain cmd]({{ site.baseurl }}/images/cmd.png "MultiChain cmd")
  
  
### Creating the Blockchain
Now that you have your command window open, we can start coding.  

#### Step:4
To create a blockchain, type the following command into the command window.  

```
multichain-util create name
```  
Replace name with the preferred name for your blockchain then press enter.
  
![MultiChain cmd]({{ site.baseurl }}/images/create.png "Create Blockchain")  

This does not actually create the blockchain but as you can see from the output the blockchain parameters
have been setup. You can view and change the parameters by editing the **params.dat** file.  

Now we runt he following command to create the blockchain.

```
multichaind name -daemon
```
![MultiChain]({{ site.baseurl }}/images/daemon.png "Create Daemon")  
  
This command starts the blockchain and runs a daemon which other nodes can connect to.
It also gives you an ip adress using which other nodes can connect to the blockchain.

### Connecting to the Blockchain
#### Step:5

Now we can connect to this blockchain from elsewhere. So we open up a command window in the MultiChain folder from another server and use the following command to connect to the blockchain.

```
multichaind name@10.226.37.163:7723
```
![MultiChain]({{ site.baseurl }}/images/request.PNG "Request Connection")  

The blockchain will successfully intialize, but you must be granted permission to connect. Copy and send the wallet address provided to you to the blockchain originator/blockchain admin. For example, the entire line ending in connect,send,receive shown below is the wallet address that needs to be sent.

#### Step:6
The user with authority to grant connection i.e. the blockchain creator must grant requests to each of the connecting nodes by running the following command.

```cmd
multichain-cli name grant 1... connect,send,receive
```
where "1..." is the adress of the server node trying to connect.  

![MultiChain]({{ site.baseurl }}/images/access_granted.png "Access Granted")
  
![MultiChain]({{ site.baseurl }}/images/multiplenodesaccess.png "Multiple Nodes Access Granted")
  
#### Step:7
After permission is granted, the new user must again type in the node address as done in Step 5 (Note, "multichaind name -daemon" could also be used here.) Successful connection to the blockchain is confirmed by "Node ready".  

Now we have our two daemon nodes running, one that created the blockchain and one that is now connected to the blockchain. Any number of nodes can connect to the blockchain. To carry out outher commands and functions we need to open up new command windows in the multichain folder. **Note: The daemon nodes should always keep running in the background as long as the blockchain is alive.**

### Creating Assets
#### Step:8
To create an asset, we need to get get the address that has the permission to create assets, so on the first server that is the node that created the blockchain we run the following

```cmd
listpermissions issue
```






  



  








  










