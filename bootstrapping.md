# Bootstrapping

By default, Geth will connect to public bootstrap nodes on startup. These public nodes give the client an entry point into the rest of the network and a way to discover additional peers.

To configure the bootnodes on startup, use the `--bootnodes` option and separate the peers by spaces. For example:
```
geth --bootnodes "enode://pubkey1@ip1 enode://pubkey2@ip2 enode://pubkey3@ip3"
```