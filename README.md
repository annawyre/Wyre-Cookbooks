# Wyre-Cookbooks

### Create an Account in Wyre
Create a [Testwyre Account](https://docs.sendwyre.com/docs/set-up-your-wyre-account) to generate a Sandbox API Key

[How to run Postman Collections](https://github.com/annawyre/Wyre-Cookbooks#run-collections-in-postman)

## Cookbooks
- [User Invoice Wallets](https://github.com/annawyre/Wyre-Cookbooks#user-invoice-wallets)
- [Decentralized Authentication](https://github.com/annawyre/Wyre-Cookbooks#decentralized-authentication)
- [3DS with Autodirect]()

## User Invoice Wallets 
Import `User Invoice Wallets.postman_collection.json` as a Collection
Import `TestWyre.postman_environment.json` as an Environment
- Add secret key
- Add master account id

#### Use wallets to reconcile incoming crypto transfers. 
* [Create User](https://docs.sendwyre.com/reference/create-user) (kyc check)
* [Create Wallet](https://docs.sendwyre.com/reference/createwallet) (masqueradeAs)
* [Create unconfirmed transfer](https://docs.sendwyre.com/reference/createtransfer), user wallet to business account
* Set up user invoice to relevant (wallet) deposit address
* [Receive wallet callback](https://docs.sendwyre.com/docs/webhooks) and validate amount
* [Confirm transfer](https://docs.sendwyre.com/reference/confirmtransfer)

## Decentralized Authentication
Import `Decentralized Authentication.postman_collection.json` as a Collection

#### Use a client-generated secretKey for Bearer authorization 
* Generate a secretKey
* [Submit Auth Token](https://docs.sendwyre.com/reference/submitauthtoken) submit the secret key as an auth token and generate a corresponding API Key
* Associate the keys to an [Account](https://docs.sendwyre.com/reference/getaccount) or [User](https://docs.sendwyre.com/reference/create-user) to activate
(for Users, a partnerId is required)

##### Run collections in Postman
![image](https://user-images.githubusercontent.com/104589640/174330245-23d189c2-eeee-41b9-b0ce-26fff71b3159.png)
