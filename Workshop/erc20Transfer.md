
# Transfer erc20

## GraphQL API

- Mutation Example
  ```javascript
  mutation erc20 {
    erc20Transfer (input: {
      contract: "0xe93e7a04a4b5273dee710f7263a4ca69b96424d3",
      to: "0xcb69b95f72d1b1f373d956d95f216492a7ea26c8"
      value: "1000000000000000000"
    }){
      transaction
      submitToken
    }
  }
  ```