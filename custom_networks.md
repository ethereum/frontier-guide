# Custom networks

Sometimes you might not need to connect to the live public network, you can instead choose to create your own private testnet. This is very useful if you don't need to test external contracts and want just to test the technology, because you won't have to compete with other miners and will easily generate a lot of test ether to play around (replace 12345 with any number):

```
geth -—networkid 12345 console
```
