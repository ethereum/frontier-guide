# Getting a client

The Frontier tool is called Geth (the old english third person singular conjugation of "to go". Quite appropriate given geth is written in Go[link]). Geth is a multipurpose command line tool that runs a full Ethereum node implemented in Go. It offers three interfaces: the command line subcommands and options [link], a Json-rpc server and an interactive console.  

In order to install Geth, open a command line or terminal tool (if you are unsure how to do this, consider waiting for a more user friendly release) and paste the command below:

`ruby -e "$(curl -fsSL https://github.com/cubedro/frontier.ethereum.org/blob/master/bin/install.rb)"`

This script will detect your OS and will attempt to install the ethereum CLI. For more options including package managers, check the OS-specific subsections.

## First run

For the purposes of this guide, we will focus on the interactive console, a JavaScript environment. The history of the console is persisted between sessions, providing for a powerful and flexible way of using the client. You can navigate your command history by using the up and down arrow keys, like a standard command line. To get started Type the code below on your terminal

`geth console`

Once geth is fully started, you should see a `>` prompt, letting you know the console is ready. To exit, type `exit` at the prompt and hit `[enter]`.

### Advanced Use

On Linux you can run one terminal with the interactive console and a second one with the logging output. First, start geth will logging:

`geth console 2>>geth.log`

Then opening a new terminal and typing `tty`. The output will be something like `/dev/pts/13`. Back in your main terminal, type: `geth console 2>> /dev/pts/13`. This will allow you to monitor your node without cluttering your console.