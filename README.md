# XDCC CLI

This project provides a simple command line tool which allow you to perform search and retrieval of files on the IRC network through the XDCC protocol.

## Features
- File search from multiple search engines.
- It allows to download multiple files at the same time.

## Installation

Assuming you have the latest version of Go installed on your system, you can use the **buid** command to get an executable:

```bash git clone https://github.com/ostafen/xdcc-cli.git
cd xdcc-cli
go build . -o xdcc
```

## Usage
To initialize a file search, simply pass a list of keywords to the **search** subcommand like so:

```bash
foo@bar:~$ xdcc search keyword1 keyword2 ...
```

For example, to search for the latest iso of ubuntu, you could simply write:

```bash
foo@bar:~$ xdcc search ubuntu iso
```

If the command succedeeds, a table, similar to the following, will be displayed:

| File Name | File Size | URL |
| :------: | :------: | :------: |
| ubuntu-20.04-desktop-amd64.iso | 2.50GB | ... |
| ... | ... | ... |

A part from file details, each row will contain an **url** of the form irc://network/channel/bot/slot, which identifies the file on the IRC network. 
To download one or more file, simply pass a list of url to the **get** subcommand like so:

```console
foo@bar:~$ xdcc get url1 url2 ... [-o /path/to/an/output/directory]
```
Alternatively, you could also specify a .txt input file, containing a list of urls (one for each line), using the **-i** switch.

## Notes

This software has been written as a development exercise and comes with no warranty. Use it at your own risk.
Moreover, the developer is not responsible for any illecit use of it.