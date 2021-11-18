# villegasblock
Proof of Authority Development Chain
For this assignment, you will take on the role of a new developer at a small bank.
Your mission, should you choose to accept it, will be to set up a testnet blockchain for your organization.
To do this, you will create and submit four deliverables:


Set up your custom testnet blockchain.


Send a test transaction.


Create a repository.


Write instructions on how to use the chain for the rest of your team.



Background
You have just landed a new job at ZBank, a small, innovative bank that is interested in exploring what
blockchain technology can do for them and their customers.
Your first project at the company is to set up a private testnet that you and your team of developers
can use to explore potentials for blockchain at ZBank.
You have decided on setting up a testnet because:
There is no real money involved, which will give your team of developers the freedom to experiment.
Testnets allows for offline development.
In order to set up a testnet, you will need to use the following skills/tools we learned in class:


Puppeth, to generate your genesis block.


Geth, a command-line tool, to create keys, initialize nodes, and connect the nodes together.


The Clique Proof of Authority algorithm.


Tokens inherently have no value here, so we will provide pre-configured accounts and nodes for easy setup.
After creating the custom development chain, create documentation for others on how to start it using the pre-configured
nodes and accounts. You can name the network anything you want, have fun with it!
Be sure to include any preliminary setup information, such as installing dependencies and environment configuration.

Instructions

Setup the custom out-of-the-box blockchain


Create a new project directory for your new network. Call it whatever you want!



Create a "Screenshots" folder inside of the project directory.


Create accounts for two (or more) nodes for the network with a separate datadir for each using geth.
![Screen Shot 2021-11-17 at 10 19 10 PM](https://user-images.githubusercontent.com/83134230/142345771-62625c6c-9371-4a76-a18b-3825aea5c691.png)


Run puppeth, name your network, and select the option to configure a new genesis block.


Choose the Clique (Proof of Authority) consensus algorithm.
![Screen Shot 2021-11-17 at 9 58 07 PM](https://user-images.githubusercontent.com/83134230/142345450-d4a235ab-f0a2-4cb0-994d-1311a1ea8ee0.png)

Paste both account addresses from the first step one at a time into the list of accounts to seal.


Paste them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.


You can choose no for pre-funding the pre-compiled accounts (0x1 .. 0xff) with wei. This keeps the genesis cleaner.
![Screen Shot 2021-11-17 at 10 23 40 PM](https://user-images.githubusercontent.com/83134230/142346175-71047107-5d37-4953-86f0-6a5433f50e8d.png)


Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.


Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.


You can delete the networkname-harmony.json file.


Screenshot the puppeth configuration once complete and save it to the Screenshots folder.
![Screen Shot 2021-11-17 at 10 26 32 PM](https://user-images.githubusercontent.com/83134230/142346425-5b425d42-b7cc-4e13-8475-af6004961057.png)


Initialize each node with the new networkname.json with geth.
![Screen Shot 2021-11-17 at 10 28 01 PM](https://user-images.githubusercontent.com/83134230/142346527-0ad3cdc2-c4da-46fb-a2ee-8d09bca1c8ce.png)


Run the first node, unlock the account, enable mining, and the RPC flag. Only one node needs RPC enabled.

![Screen Shot 2021-11-17 at 10 29 29 PM](https://user-images.githubusercontent.com/83134230/142346626-7b6853cb-756c-4741-9ad7-983defac835d.png)

Set a different peer port for the second node and use the first node's enode address as the bootnode flag.


Be sure to unlock the account and enable mining on the second node!

![Screen Shot 2021-11-17 at 10 00 21 PM](https://user-images.githubusercontent.com/83134230/142346709-7b5618ed-4864-4662-a76d-05e84db7ad36.png)

You should now see both nodes producing new blocks, congratulations!



Send a test transaction
![Screen Shot 2021-11-17 at 9 49 44 PM](https://user-images.githubusercontent.com/83134230/142347014-d581c0a0-be4b-446a-89b4-ffad6cb73640.png)


Use the MyCrypto GUI wallet to connect to the node with the exposed RPC port.

![Screen Shot 2021-11-17 at 9 08 30 PM](https://user-images.githubusercontent.com/83134230/142346980-afc82a5f-3f0d-4237-9da5-cd860dc7fec8.png)

![Screen Shot 2021-11-17 at 9 23 02 PM](https://user-images.githubusercontent.com/83134230/142347006-90430ec9-9bd0-4aef-b7be-39fb4e7e7f31.png)

You will need to use a custom network, and include the chain ID, and use ETH as the currency.

![Screen Shot 2021-11-17 at 10 32 25 PM](https://user-images.githubusercontent.com/83134230/142346963-0ace5dc5-c203-433d-a118-9168db45045a.png)




Import the keystore file from the node1/keystore directory into MyCrypto. This will import the private key.

![Screen Shot 2021-11-17 at 9 23 02 PM](https://user-images.githubusercontent.com/83134230/142347062-7bb9a7ec-9bab-4b38-8584-cf5504d895a6.png)

Send a transaction from the node1 account to the node2 account.


Copy the transaction hash and paste it into the "TX Status" section of the app, or click "TX Status" in the popup.


Screenshot the transaction metadata (status, tx hash, block number, etc) and save it to your Screenshots folder.


Celebrate, you just created a blockchain and sent a transaction!




Create a repository, and instructions for launching the chain


Create a README.md in your project directory and create documentation that explains how to start the network.


Remember to include any environment setup instructions and dependencies.


Be sure to include all of the geth flags required to get both nodes to mine and explain what they mean.


Explain the configuration of the network, such as it's blocktime, chain ID, account passwords, ports, etc.


Explain how to connect MyCrypto to your network and demonstrate (via screenshots and steps) and send a transaction.


Upload the code, including the networkname.json and node folders.



Remember, never share your mainnet private keys! This is a testnet, so coins have no value here!

Hints


If you get stuck - try our step by step PoA Guide located here.


If you aren't seeing any movement in the wallet amounts in MyCrypto after sending/receiving transactions, try the following:

Terminate both nodes using control+C in the Node1 and Node2 terminal windows.
Change networks in MyCrypto to a Testnet such as Kovan.
Restart Node1 and Node2 in their terminal windows.
Reconnect to your network in MyCrypto.
Log into your wallet and refresh the amount.



If that doesn't help make sure you are sending a large enough sum of ETH to see actual movement in the digits. You may have to click on the amount itself to see the full value down to the WEI.




Submission


Include all appropriate requirements in a GitHub repository.


Submit the link to your GitHub repository to Bootcamp Spot.




Requirements

Setup and Testing  (50 points)

To receive all points, your code must:

Set up the custom Testnet Blockchain. (14 points)
Follow and test the directives for set up as indicated. (12 points)
Send test transactions. (12 points)
Send multi-node test transactions. (12 points)


Markdown Documentation (20 points)

To receive all points, your code must:

Include appropriate screenshots of steps and transactions in the ReadME.md file. (10 points)
Provide a detailed description of the steps for setting up the network and include screenshots of the process in the ReadME.md. (10 points)


Coding Conventions and Formatting (10 points)

To receive all points, your code must:

Place imports at the beginning of the file, just after any module comments and docstrings and before module globals and constants. (3 points)
Name functions and variables with lowercase characters and with words separated by underscores. (2 points)
Follow Don't Repeat Yourself (DRY) principles by creating maintainable and reusable code. (3 points)
Use concise logic and creative engineering where possible. (2 points)


Deployment and Submission (10 points)

To receive all points, you must:

Submit a link to a GitHub repository that’s cloned to your local machine and contains your files. (5 points)
Include appropriate commit messages in your files. (5 points)


Code Comments (10 points)

To receive all points, your code must:

Be well commented with concise, relevant notes that other developers can understand. (10 points)


© 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
