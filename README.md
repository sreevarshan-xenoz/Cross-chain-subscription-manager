Cross-Chain Subscription Manager

Overview

Installing Yarn
This will install yarn, and verify it is installed correctly. Install yarn by either running npm install --global yarn, or visit https://classic.yarnpkg.com/en/docs/install for more information. See below, corepack enable will add the Corepack shims to the install directories, and yarn --version will verify yarn is installed correctly.

sh
corepack enable
yarn --version # for verification
This app uses Yarn 1, so running the above command will show a version in the format 1.x.x. If you are using a different version of yarn, you can use yarn set version <version> to switch like in the example below.

sh
yarn set version 1.22.5
Installing Docker
Installing Docker
Creating Your Dapp From a Template
Now you'll use yarn to pull down the sample dapp. The sample dapp will be placed in a subfolder named demo.

sh
yarn create @agoric/dapp demo
Installing Dapp Dependencies
Now navigate to the demo directory and run the yarn install command to install any solution dependencies.

Downloading all the required dependencies may take several minutes. The UI depends on the React framework, and the contract depends on the Agoric framework. The packages in this project also have development dependencies for testing, code formatting, and static analysis.

sh
cd demo
sh
yarn install
Troubleshooting yarn install
Starting a Local Agoric Blockchain
Now go ahead and start a local Agoric blockchain using the yarn start:docker command. Note: This container is several gigabytes in size and may take a few minutes to download.

sh
yarn start:docker
Once the network has started you can check the logs. Once you see messages showing blocks with a status of commit you can rest assured the network is running properly.

sh
yarn docker:logs
Your output should resemble this:


demo-agd-1  | 2023-12-27T04:08:06.384Z block-manager: block 1003 begin
demo-agd-1  | 2023-12-27T04:08:06.386Z block-manager: block 1003 commit
demo-agd-1  | 2023-12-27T04:08:07.396Z block-manager: block 1004 begin
demo-agd-1  | 2023-12-27T04:08:07.398Z block-manager: block 1004 commit
demo-agd-1  | 2023-12-27T04:08:08.405Z block-manager: block 1005 begin
demo-agd-1  | 2023-12-27T04:08:08.407Z block-manager: block 1005 commit
Starting the Dapp Smart Contract
Use control-C to exit the logs, then start the smart contract. Starting the contract may take a minute or two, so after running this command proceed to the next step.

sh
yarn start:contract
Behind the Scenes
Setting up a Keplr Wallet Demo Account
Next, ensure you have the Keplr wallet plug-in installed.

Installing Keplr Wallet
WARNING

Remember, this is just a demo. In real-world scenarios ensuring proper security around mnemonic phrases is critical!

For any mnemonic phrase you use to secure your own assets, take care to keep it strictly confidential! The mnemonic here is only for testing.
Using a separate browser profile is a good way to avoid accidentally using the wrong account when testing vs. with real assets.
Once the plug-in has been installed, open Keplr and select the option to Import an existing wallet. Then choose the option to Use recovery phrase or private key.

Choose the "Import an Existing Wallet" option

Choose the "Use recovery phrase or private key" option

To import your wallet, you'll need to copy the following mnemonic phrase into Keplr.


spike siege world rather ordinary upper napkin voice brush oppose junior route trim crush expire angry seminar anchor panther piano image pepper chest alone
Pasting the mnemonic phrase
Give your new wallet a name and a password. Click Next.
In the next step, do not select any **chains** except for **Cosmos Hub**. Click "Save".
Starting the Dapp
Start the UI for the sample dapp.

sh
yarn start:ui
Note the localhost link that appears on your terminal window. Open this link in your browser.

Running the  command

Open the link in your browser

From the browser UI, click the "Connect Wallet" button to connect your Keplr wallet.

Adding Agoric local to Keplr
Making an Offer
Once your wallet is connected, click on the "Make Offer" button to purchase 3 properties. Approve the transaction in your Keplr wallet.

Making an offer

When the transaction is complete you will notice some IST has been debited from your wallet, and you are the owner of three new properties. Feel free to experiment with offering less than the required 0.25 IST or attemping to purchase more than three items. You'll see these offers will not be accepted. Conditional offers like this are a key part of the Agoric platform!

Finished transaction

Congratulations! You got your first Agoric dapp up and running! Now that you've got your first Agoric dapp up and running, let's focus on some key takeaways from this exercise:

Starting an Agoric Chain: You have gained experience starting a local Agoric blockchain.

Deploying a Contract: You have deployed a smart contract onto the Agoric platform! Note: testnet deployment, faucets, etc. are discussed later.

Making an Offer: Finally, you've learned to make an offer and seen that offer constraints are enforced by the Agoric platform. This means user interface can't attempt to fool a user by showing a 0.25 IST when actually charging them a much higer amount, such as 500 IST. It's also important to note that the contract cannot take the 0.25 IST without satisfying the want constraint, nor can the contract take more than the 0.25 cents in the give contraint.



The Cross-Chain Subscription Manager is designed to simplify subscription management by leveraging blockchain technology. It uses Agoric smart contracts and IBC (Inter-Blockchain Communication) to enable seamless cross-chain payments. This tool is a lightweight, efficient solution for managing subscriptions across multiple blockchains with minimal setup.

Features

	•	Subscription List Management:
Easily add, edit, and view active subscriptions in a clean and minimal UI.
	•	Automated Payments:
Never miss a payment! Automates recurring payments using Agoric smart contracts.
	•	Cross-Chain Execution:
Supports payments across multiple chains through IBC integration.
	•	Timer-based Triggers:
Handles recurring subscriptions with precise time-based triggers.

Business Model

This project demonstrates the potential of blockchain for managing subscription-based models. Future applications could target:
	1.	SaaS Companies: Offering blockchain-based recurring payment systems.
	2.	Content Creators: Managing subscriptions for premium content.
	3.	DeFi Ecosystems: Automating staking/unstaking subscriptions.

Potential monetization includes transaction fees, premium features, or licensing the framework to enterprises.

Feature Scope

Here’s what we’re building now and ideas for the future:

Current Scope (Hackathon MVP):

	•	Basic subscription management UI (React).
	•	Agoric-based smart contract for recurring payments.
	•	IBC integration for cross-chain capabilities.

Future Enhancements:

	•	Multi-user authentication with wallet integration.
	•	Analytics dashboard for tracking subscription data.
	•	Notifications/reminders for payments via email or decentralized messengers.
	•	Support for additional chains like Polkadot, Ethereum, etc.

How to Run
Installing Yarn
This will install yarn, and verify it is installed correctly. Install yarn by either running npm install --global yarn, or visit https://classic.yarnpkg.com/en/docs/install for more information. See below, corepack enable will add the Corepack shims to the install directories, and yarn --version will verify yarn is installed correctly.

sh
corepack enable
yarn --version # for verification
This app uses Yarn 1, so running the above command will show a version in the format 1.x.x. If you are using a different version of yarn, you can use yarn set version <version> to switch like in the example below.

sh
yarn set version 1.22.5
Installing Docker
Installing Docker
Creating Your Dapp From a Template
Now you'll use yarn to pull down the sample dapp. The sample dapp will be placed in a subfolder named demo.

sh
yarn create @agoric/dapp demo
Installing Dapp Dependencies
Now navigate to the demo directory and run the yarn install command to install any solution dependencies.

Downloading all the required dependencies may take several minutes. The UI depends on the React framework, and the contract depends on the Agoric framework. The packages in this project also have development dependencies for testing, code formatting, and static analysis.

sh

cd demo
sh

yarn install


Starting a Local Agoric Blockchain


Now go ahead and start a local Agoric blockchain using the yarn start:docker command. Note: This container is several gigabytes in size and may take a few minutes to download.

sh


yarn start:docker

Once the network has started you can check the logs. Once you see messages showing blocks with a status of commit you can rest assured the network is running properly.

sh

yarn docker:logs



Your output should resemble this:


demo-agd-1  | 2023-12-27T04:08:06.384Z block-manager: block 1003 begin
demo-agd-1  | 2023-12-27T04:08:06.386Z block-manager: block 1003 commit
demo-agd-1  | 2023-12-27T04:08:07.396Z block-manager: block 1004 begin
demo-agd-1  | 2023-12-27T04:08:07.398Z block-manager: block 1004 commit
demo-agd-1  | 2023-12-27T04:08:08.405Z block-manager: block 1005 begin
demo-agd-1  | 2023-12-27T04:08:08.407Z block-manager: block 1005 commit
Starting the Dapp Smart Contract
Use control-C to exit the logs, then start the smart contract. Starting the contract may take a minute or two, so after running this command proceed to the next step.

sh
yarn start:contract
Behind the Scenes
Setting up a Keplr Wallet Demo Account
Next, ensure you have the Keplr wallet plug-in installed.

Installing Keplr Wallet
WARNING

Remember, this is just a demo. In real-world scenarios ensuring proper security around mnemonic phrases is critical!

For any mnemonic phrase you use to secure your own assets, take care to keep it strictly confidential! The mnemonic here is only for testing.
Using a separate browser profile is a good way to avoid accidentally using the wrong account when testing vs. with real assets.
Once the plug-in has been installed, open Keplr and select the option to Import an existing wallet. Then choose the option to Use recovery phrase or private key.

Choose the "Import an Existing Wallet" option

Choose the "Use recovery phrase or private key" option

To import your wallet, you'll need to copy the following mnemonic phrase into Keplr.


spike siege world rather ordinary upper napkin voice brush oppose junior route trim crush expire angry seminar anchor panther piano image pepper chest alone
Pasting the mnemonic phrase
Give your new wallet a name and a password. Click Next.
In the next step, do not select any **chains** except for **Cosmos Hub**. Click "Save".
Starting the Dapp
Start the UI for the sample dapp.

sh
yarn start:ui
Note the localhost link that appears on your terminal window. Open this link in your browser.

Running the  command

Open the link in your browser

From the browser UI, click the "Connect Wallet" button to connect your Keplr wallet.

Adding Agoric local to Keplr
Making an Offer
Once your wallet is connected, click on the "Make Offer" button to purchase 3 properties. Approve the transaction in your Keplr wallet.

Making an offer

When the transaction is complete you will notice some IST has been debited from your wallet, and you are the owner of three new properties. Feel free to experiment with offering less than the required 0.25 IST or attemping to purchase more than three items. You'll see these offers will not be accepted. Conditional offers like this are a key part of the Agoric platform!

Finished transaction

Congratulations! You got your first Agoric dapp up and running! Now that you've got your first Agoric dapp up and running, let's focus on some key takeaways from this exercise:

Starting an Agoric Chain: You have gained experience starting a local Agoric blockchain.

Deploying a Contract: You have deployed a smart contract onto the Agoric platform! Note: testnet deployment, faucets, etc. are discussed later.

Making an Offer: Finally, you've learned to make an offer and seen that offer constraints are enforced by the Agoric platform. This means user interface can't attempt to fool a user by showing a 0.25 IST when actually charging them a much higer amount, such as 500 IST. It's also important to note that the contract cannot take the 0.25 IST without satisfying the want constraint, nor can the contract take more than the 0.25 cents in the give contraint.




	1.	Spin up Agoric Environment:
Set up the Agoric CLI and deploy the subscription management contract.
	2.	Run the Frontend:

cd frontend  
npm install  
npm start  

Open the app in your browser at http://localhost:5173.

	3.	Interact with the Contract:
Use the frontend to connect your wallet, add subscriptions, and test cross-chain payments.

Demo Video

Check out our quick walkthrough here: 

Developer Contact

We’re here to help if you have questions or feedback!
	•	Team Lead: [Your Name]
	•	Email: [Your Email Address]
	•	GitHub: [Your GitHub Link]
	•	LinkedIn: [Your LinkedIn Link]

Let me know if you need any changes or additional sections!
