# LinearProtocol



## Install the Library

The best way to interact with our API is to use our NodeJS library:

```
//install via NPM 
npm install linearprotocol

```
## Create a Node           

In the current version of LinearProtocol, we rely on web3.storage APIs for our minting requirements.

### Parameters:

- username (String): User-choice name of node. Used in public key encryption
- seed (String): Seed word used to validate ownership of node
- nft_token (String): nft.storage user token
- w3token (String): web3.storage user token

```
//register node 
import {registerUser} from 'linearprotocol/assign'

await registerUser(username, seed, nft_token, w3token)

//returns IPNS file (user public ID) and key wallet private key

```

## Mint Media 

Mint crendential using custom crendential object. 

### Parameters:

- creator (String): Name of minter
- itemName (String): Name of media
- credential_obj (Object): Object for custom credential creation
- recipient (String): public address of recipient
- w3token (String): web3.Storage token of minter
- account_private_key (String): Account key used to access keyvault 

```
//mint credential
import {mint_nonmedia} from 'linearprotocol/assign'

await mint_nonmedia(creator, itemName, credential_obj, recipient, w3token, account_private_key)

```
The above function call returns the dweb link that points provides the proposal link necessary recipients to claim media. 

## Claim Crendential Ownership

Claim confirm credential ownership. 

### Parameters:

- creator (String): Name of minter
- file (String): IPNS file name
- w3token (String): web3.Storage token of minter

```
//mint credential
import {claim_media} from 'linearprotocol/assign'

await mint_nonmedia(creator, file, w3token)

```

## Validate Credential

Validate history of file and ownership. 

### Parameters:

- creator (String): Name of minter
- owner (String): Claimed owner of credentials 
- ipns (String): IPNS file name
- token (String): web3.Storage token of minter

```
//mint credential
import {validate_ownership} from 'linearprotocol/assign'

await mint_nonmedia(creator, owner, ipns,token)

```





