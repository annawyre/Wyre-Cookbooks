# Wyre-Cookbooks

### Create an Account in Wyre
Create a [Testwyre Account](https://docs.sendwyre.com/docs/set-up-your-wyre-account) to generate a Sandbox API Key

[How to run Postman Collections](https://github.com/annawyre/Wyre-Cookbooks#run-collections-in-postman)

|Variable|Value|
|--------|-----|
|api_base_url - Test|https://api.testwyre.com|
|api_base_url - Prod|https://api.sendwyre.com|
|WYRE_TOKEN|Your Wyre Private Key|
|ACCOUNT_ID|Your Wyre Partner Account ID|


## Cookbooks
- [User Invoice Wallets](https://github.com/annawyre/Wyre-Cookbooks#user-invoice-wallets)
- [Decentralized Authentication](https://github.com/annawyre/Wyre-Cookbooks#decentralized-authentication)
- [3DS with Autodirect](https://github.com/annawyre/Wyre-Cookbooks#3ds-with-autoredirect)
- [MoneyGram](https://github.com/annawyre/Wyre-Cookbooks/blob/main/Moneygram.postman_collection.json)

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

## 3DS with Autoredirect
Import `3DS Auto Redirect.postman_collection.json` as a Collection

Import `TestWyre.postman_environment.json` as an Environment
- Add secret key
- Add master account id

#### Key Parameters
- `/v3/orders/reserve` Specify custom success page in “redirectUrl” parameter and include “autoRedirect” : true
- `/v3/debitcard/process/partner` Include "trigger3ds": true
- `/v3/debitcard/authorization/{{walletOrderId}}/with-redirection` will return "authorization3dsUrl" for the 3ds challenge
  - Option to display url in an iframe: `<iframe src="{{authorization3dsUrl}}"></iframe>`

## MoneyGram
Import `Moneygram.postman_collection.json` as a Collection
- Add secret key
- Add master account id

### Payout to thousands of Moneygram locations around the world
* [Create User](https://docs.sendwyre.com/reference/create-user) (kyc check)
* [Create Wallet](https://docs.sendwyre.com/reference/createwallet) (masqueradeAs)
* [Create Transfer](https://docs.sendwyre.com/reference/createtransfer) (masqueradeAs)
* Navigate user to `completeDepositUrl`
* Provide `more_info_url` to user

##### Run collections in Postman
![image](https://user-images.githubusercontent.com/104589640/174330245-23d189c2-eeee-41b9-b0ce-26fff71b3159.png)
