
# Create Airdrop

## GraphQL API

- Query String
  ```
  mutation createAirdropMission($input: CreateAirdropMissionInput!) {
    createAirdropMission(input: $input) {
      pendingTransactions
      transaction
      submitToken
    }
  }
  ```
- Query Variables

  ```
  {  
    "input":{  
        "listId":"QWlyZHJvcExvY2F0ZToxMDg=",
        "itemId":"VG9rZW46woDDssO6wrLCuxERw6jCp3zCqypmwp7CjsO/",
        "budget":"1000000000000000000000",
        "invokeTime":"1543819592000"
    }
  }
  ```
- HTTP Headers 
  ```
  {
    "accept": "application/json",
    "content-type": "application/json",
    "authorization": "bearer eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCIsImtpZCI6ImZzdGstZW5naW5lIn0.eyJ1aWQiOiLDr1xiw73Ch8KDSFx1MDAxMcOowo5awrvCqsOAXHUwMDAywrwmIiwiaWF0IjoxNTM4NTYyODAyLCJleHAiOjE1Mzg2NDkyMDIsImF1ZCI6InVybjpmc3RrOmVuZ2luZSIsImlzcyI6InVybjpmc3RrOmVuZ2luZSIsInN1YiI6InVybjpmc3RrOmVuZ2luZTphY2Nlc3NfdG9rZW4ifQ.sGfxYe16aRx_vmvzlRps_gcyTeQD-zsR5HCtjXQ3hYpQYjN1lOFkdpF0m4Yrrh8uHyWBYifqYUVHmkRej4-9gA"
  }
  ```
## HTTP Request

- URL
  - For development: `https://test.fstk.io/api`
  - For production: `https://engine.fstk.io/api`

- Method: `POST`

- Headers
  - accept: `application/json`
  - content-type: `application/json` 
  - authorization: `Bearer [JWT Web-to-Server access token]`
    - (for example)
      ```
      Bearer eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCIsImtpZCI6ImZzdGstZW5naW5lIn0.eyJ1aWQiOiLDr1xiw73Ch8KDSFx1MDAxMcOowo5awrvCqsOAXHUwMDAywrwmIiwiaWF0IjoxNTM4NzA5MDM2LCJleHAiOjE1Mzg3OTU0MzYsImF1ZCI6InVybjpmc3RrOmVuZ2luZSIsImlzcyI6InVybjpmc3RrOmVuZ2luZSIsInN1YiI6InVybjpmc3RrOmVuZ2luZTphY2Nlc3NfdG9rZW4ifQ.msJZ61FHIkKtjUpDs4sx1Kk1rb9vdhus3ntUDj6rHNmsygiHTgOEMQFJMtVqtWqkNgrtRgGpngq8Rf47xTT53g
      ```

- Body
  ``` 
  {  
    "query":"    mutation createAirdropMission($input: CreateAirdropMissionInput!) {      createAirdropMission(input: $input) {        pendingTransactions,        transaction,        submitToken      }    }",
    "variables":{  
        "mission":{  
          "listId":"QWlyZHJvcExvY2F0ZToxMDg=",
          "itemId":"VG9rZW46woDDssO6wrLCuxERw6jCp3zCqypmwp7CjsO/",
          "budget":"1000000000000000000000",
          "invokeTime":"1543819592000"
        }
    }
  }
  ```

  The value of `query` in the body is a `String`. 
  

## HTTP Response
```
{  
   "data":{  
      "createAirdropMission":{  
         "pendingTransactions":"0",
         "transaction":{  
            "nonce":"0xee",
            "gasPrice":"0x3b9aca00",
            "gas":"0x31a46",
            "to":"0x37113085b9fF3F7d0933110357084961F5Be603a",
            "value":"0x0",
            "data":"0x4000aea0000000000000000000000000c3a86fb0204dcb008372774960400b65fec3a6b200000000000000000000000000000000000000000000003635c9adc5dea00000000000000000000000000000000000000000000000000000000000000000006000000000000000000000000000000000000000000000000000000000000000642a0691ae00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000005c04d14800000000000000000000000000000000000000000000000000000000",
            "chainId":42
         },
         "submitToken":"eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCIsImtpZCI6ImZzdGstZW5naW5lIn0.eyJ1aWQiOiLDr1xiw73Ch8KDSFx1MDAxMcOowo5awrvCqsOAXHUwMDAywrwmIiwiYWN0aW9uIjoiY3JlYXRlQWlyZHJvcE1pc3Npb24iLCJkYXRhIjoiUUFDdW9BQUFBQUFBQUFBQUFBQUFBTU9vYjdBZ1Rjc0FnM0ozU1dCQUMyWCt3NmF5QUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQTJOY210eGQ2Z0FBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBWUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQmtLZ2FScmdBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQVhBVFJTQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUE9IiwiaW5mbyI6eyJsaXN0VHlwZSI6IkFpcmRyb3BMb2NhdGUiLCJsaXN0SWQiOiIxMDgiLCJlc2Nyb3dib3hBZGRyZXNzIjoiMHhjM2E4NmZCMDIwNGRDQjAwODM3Mjc3NDk2MDQwMEI2NUZlYzNhNmIyIiwidXNlckFkZHJlc3MiOiIweGNiNjliOTVmNzJkMWIxZjM3M2Q5NTZkOTVmMjE2NDkyYTdlYTI2YzgiLCJpdGVtSWQiOiLCgMOyw7rCssK7XHUwMDExXHUwMDExw6jCp3zCqypmwp7CjsO_IiwiaXRlbVR5cGUiOiJUb2tlbiIsIml0ZW1BZGRyZXNzIjoiMHgzNzExMzA4NWI5ZmYzZjdkMDkzMzExMDM1NzA4NDk2MWY1YmU2MDNhIiwiYnVkZ2V0IjoiMTAwMDAwMDAwMDAwMDAwMDAwMDAwMCIsImludm9rZVRpbWUiOjE1NDM4MTk1OTIwMDB9LCJpYXQiOjE1NDM4MTk1NjIsImV4cCI6MTU0MzgyMDE2MiwiYXVkIjoidXJuOmZzdGs6ZW5naW5lIiwiaXNzIjoidXJuOmZzdGs6ZW5naW5lIiwic3ViIjoidXJuOmZzdGs6ZW5naW5lOnN1Ym1pdF90b2tlbiJ9.ZLiiDk-RyMG5JZtl8esl85UtSwOhw6RkKY1N45KkRp6AsL9hoBT1kYJLyoZS5uLoVkgDj8HZ9nIQEUwoPfiy9Q"
      }
   }
}
```

This API responses a ABI-Encoded transaction for creating the basic voucher campaign, and the end-user (the sender, the requester) has to sign the `transaction` object in the response via [ETH Key lib JS](https://github.com/funderstoken/eth-key-lib-js), then send the signed transaction and the `submitToken` to [SubmitSignedTransaction API](https://github.com/funderstoken/module-api/tree/master/SubmitSignedTransaction).


## Parameters
### Request 
  - `listId`: ID of the airdrop list.
  - `itemId`: ID of the item(token/voucher) to drop.
  - `budget`: Budget for the airdrop. The format is Decimaled Number.
  - `invokeTime`: The airdrop invoke time. The format is Unix Timestamp in millisecond resolution.

### Response
  - `transaction`: UNSIGNED raw transaction format in Ethereum.
  - `submitToken`: The value for [SubmitSignedTransaction API](https://github.com/funderstoken/module-api/tree/master/SubmitSignedTransaction).