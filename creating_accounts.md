# Creating accounts

_Copied from https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts_

### Creating a new account

```
geth account new
```

Creates a new account and prints the address.

On the console, use:

```
> admin.newAccount()
```

The account is saved in encrypted format, you are prompted for a passphrase. You **must** remember this passphrase to unlock your account in the future.

For non-interactive use the passphrase can be specified with the --password flag:

```
geth --password <passwordfile> account new
```

Note, this is meant to be used for testing only, it is a bad idea to save your
password to file or expose in any other way.

### Creating an account by importing an EC private key (binary)

```
import [arguments...]


    geth account import <keyfile>
```

Imports an unencrypted private key from <keyfile> and creates a new account.
Prints the address.

The keyfile is assumed to contain an unencrypted private key in canonical EC
raw bytes format.

The account is saved in encrypted format, you are prompted for a passphrase.

You must remember this passphrase to unlock your account in the future.

For non-interactive use the passphrase can be specified with the -password flag:

```
geth --password <passwordfile> account import <keyfile>
```

Note:
As you can directly copy your encrypted accounts to another ethereum instance,
this import mechanism is not needed when you transfer an account between
nodes.

**Note**:
Since you can directly copy your encrypted accounts to another ethereum instance, this import/export mechanism is not needed when you transfer an account between nodes.

**Warning:**
If you use the password flag with a password file, best to make sure the file is not readable or even listable for anyone but you. You achieve this with:

```
touch /path/to/password 
chmod 700 /path/to/password
cat > /path/to/password
>I type my pass here^D
```