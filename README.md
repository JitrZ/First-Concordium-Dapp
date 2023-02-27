## Building Dapp Steps
First node js & npm installed.
Then going to the project folder and created a folder for the Dapp.
Use `npm init` to create a json project, name the package.
three packages need to be installed:
`npm install @concordium/web-sdk@3.1.0`
`npm install @concordium/browser-wallet-api-helpers@2.0.0`
`npm install live-server@1.2.2`

Now time to edit the package.json file to edit the scripts commands. also create the index.html file and work on the frontend. 
The codes used is mostly from [here](https://github.com/Concordium/voting-workshop/tree/main/dapp).

The script for package.json:

`"start": "live-server index.html --mount=/sdk.js:./node_modules/@concordium/web-sdk/lib/concordium.min.js --mount=/helpers.js:./node_modules/@concordium/browser-wallet-api-helpers/lib/concordiumHelpers.min.js"`

Editing index.html file here is done step by step according to [the workshop](https://www.youtube.com/watch?v=J-SP_ptKu_I)

Instantiated contract 'e_democracy' with address: <3547,0> with this txn hash: 727a2a228c589b669ee620a78ff0e645069d25e8835439263b1ff6264becfeb0

The changes done in compare to the index file from workshop are:
1- It checks for wallet connection even for voting creation too.
2- Instead of `addNonMembership`, used `addMembership` in *idCheckedVote fuction*, so that only people of that country can take part in election votings.
p.s: as the testnet account id is for DK, it checks countryOfResidence with ['DK'].
3- As it was for testing, it hasn't changed, but it can restrict access to create voting for specific accounts. For example, 
only political parties' candidates create voting. Also, put vote and view results section in another page available to all. People (users) just must have 
the index of related voting contract to vote and view the results.

## Using the Dapp
Instructions:
1. Run `npm install` to install the dependencies.
2. Run the app with `npm start`.
Note that for using the dapp, you need the Concordium Wallet browser extension.