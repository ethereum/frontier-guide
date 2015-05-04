# Managing accounts

_Copied from https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts_

**WARNING**
Remember your password. 

If you lose the password you use to encrypt your account, you will not be able to access that account.
Repeat: It is NOT possible to access your account without a password and there is no _forgot my password_ option here. Do not forget it.

## Account management
The ethereum CLI `geth` provides account management via the `account` subcommand:

```
account command [arguments...]
```

Manage accounts lets you create new accounts, list all existing accounts,
import a private key into a new account.

It supports interactive mode, when you are prompted for password as well as
non-interactive mode where passwords are supplied via a given password file.
Non-interactive mode is only meant for scripted use on test networks or known
safe environments.

Make sure you remember the password you gave when creating a new account (with
either new or import). Without it you are not able to unlock your account.

Note that exporting your key in unencrypted format is NOT supported.

Keys are stored under `<DATADIR>/keys`. Make sure you backup your keys regularly! It is safe to transfer the entire directory or the individual keys therein between ethereum nodes.

And finally. **DO NOT FORGET YOUR PASSWORD**

```
SUBCOMMANDS:

        list    print account addresses
        new     create a new account
        import  import a private key into a new account

```

You can get info about further subcommands by `geth account help <subcommand>`

## Examples
### Interactive use

```
$ geth -datadir /tmp/eth  account new
The new account will be encrypted with a passphrase.
Please enter a passphrase now.
Passphrase:
Repeat Passphrase:
Address: {7f444580bfef4b9bc7e14eb7fb2a029336b07c9d}

$ geth -datadir /tmp/eth  account list
Address: {7f444580bfef4b9bc7e14eb7fb2a029336b07c9d}

$ geth -datadir /tmp/eth.0  account import ./key.prv
The new account will be encrypted with a passphrase.
Please enter a passphrase now.
Passphrase:
Repeat Passphrase:
Address: {7f444580bfef4b9bc7e14eb7fb2a029336b07c9d}
```

### Non-interactive use 
You supply a plaintext password file as argument to the `-password` flag.  

**Note**: 
Supplying the password directly as part of the command line is not encouraged, but you can always use shell trickery to get round this restriction.

```
$ geth -datadir /tmp/eth -password /path/to/password account new
Address: b0047c606f3af7392e073ed13253f8f4710b08b6

$ geth -datadir /tmp/eth account list
Address: {b0047c606f3af7392e073ed13253f8f4710b08b6}

$ geth -datadir /tmp/eth1 -password /path/to/anotherpassword account import ./key.prv
Address: b0047c606f3af7392e073ed13253f8f4710b08b6
```