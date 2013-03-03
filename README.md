# Overview
Fishtest is a distributed task queue for testing chess engines.  It is currently being used
for testing changes on Stockfish with tens of thousands of games per change. The following
setup describes a step-by-step installation for a machine that will run test matches.

## Setup

It's recommended to create a new user for running fishtest
```
$ sudo useradd fishtest
$ sudo passwd fishtest
$ su fishtest
$ cd ~
```

### Clone fishtest

You will need the fishtest repository, as well as some python prereqs.
```
$ git clone https://github.com/glinscott/fishtest.git
$ sudo pip install pymongo
$ sudo pip install requests
$ sudo pip install sh
```

### Create testing directory

This is where the matches will be run
```
$ cd ~
$ mkdir testing

Edit ~/.bash_profile and add
export FISHTEST_DIR=~/testing
```

Get cutechess-cli
TODO!

## Launching the worker

```
$ cd ~/fishtest
$ ./start_worker.sh
```

## Running the website

This is only if you wish to run your own testing environment (ie. you are testing changes on another engine).

To launch a development version of the site, you can simply do:
```
cd ~/fishtest/fishtest
sudo python setup.py develop
./start.sh
```