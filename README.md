# Wyre-Cookbooks

#### Create a [Testwyre Account](https://docs.sendwyre.com/docs/set-up-your-wyre-account) to generate a Sandbox API Key

#### Import `User Invoice Wallets.postman_collection.json` as a Collection

#### Import `TestWyre.postman_environment.json` as an Environment
- Add secret key
- Add master account id

#### Run in Postman

![image](https://user-images.githubusercontent.com/104589640/174330245-23d189c2-eeee-41b9-b0ce-26fff71b3159.png)



## User Invoice Wallets
Use wallets to reconcile incoming crypto transfers. 
* [Create User](https://docs.sendwyre.com/reference/create-user) (kyc check)
* [Create Wallet](https://docs.sendwyre.com/reference/createwallet) (masqueradeAs)
* [Create unconfirmed transfer](https://docs.sendwyre.com/reference/createtransfer), user wallet to business account
* Set up user invoice to relevant (wallet) deposit address
* [Receive wallet callback](https://docs.sendwyre.com/docs/webhooks) and validate amount
* [Confirm transfer](https://docs.sendwyre.com/reference/confirmtransfer)
