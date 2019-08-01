
# Create a role

## GraphQL API

- Mutation Example
  ```javascript
  mutation createUserV2 {
    createUserV2(
      input: {
        id: "issuer_abc"
        password: "12345678"
        userPassphrase: "12345678"
        role: 1
        etherValue: "2000000000000000" # 0.002 ether
        masterTokenValue: "2000000000000000" # 0.002 master token
        tokenId: "658968545"
        tokenUri: "658968545"
        masterPassphrase: "12345678"
      }
    ) {
      uid
      keystore
      etherTransaction
      masterTokenTransaction
      mintILTransaction
    }
  }
  ```