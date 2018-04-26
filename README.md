# Compiling
Compile the OID Daemon

Note: Use Linux Ubuntu 14.04 (recommended) If you plan to use Ubuntu 16.04+ please see our troubleshooting guide.

Go here -> https://github.com/OidLife/Troubleshooting

# Opioid compile from source:
1) ```sudo apt-get update```

2) ```sudo apt-get upgrade```

3) ```sudo apt-get install -y git make g++ build-essential libminiupnpc-dev```

4) ```sudo apt-get install libssl-dev libdb-dev libdb++-dev libboost-all-dev git libssl1.0.0-dbg```

5) ```sudo apt-get install libdb-dev libdb++-dev libboost-all-dev libminiupnpc-dev libminiupnpc-dev```

6) ```sudo apt-get install libevent-dev libcrypto++-dev libgmp3-dev```

## ** Make sure the above installs without error. If any errors, the remaining will not install.

7) ```mkdir oid_source```

8) ```cd oid_source```

9) download the source code https://github.com/OidLife/opioid-oid-project or use command line  
`wget https://oid.life/source/opioid-source.tar.gz`

10) ```tar -xzvf opioid-source.tar.gz```

11) ```rm examplecoin-source.tar.gz```

12) ```cd src```

13) ```make -f makefile.unix RELEASE=1```

### *** The compiling will take about 15 to 30 minutes depending on your system. ***

### *** Your compiled daemon named opioidd can be found in the src folder when compiling is finished.

14) ```chmod +x opioidd```

15) ```sudo mv opioidd /usr/bin/```

16) ```cd ~```

17) ```mkdir .opioid```

18) ```sudo nano opioid.conf``` (or your preferred editor)

19) Paste in to the config:
```
rpcuser=YOUR USERNAME
rpcpassword=YOUR PASSWORD
rpcallowip=YOUR LOCALHOST IP
rpcport=36362
listen=1
server=1
daemon=1 #<-keep this at 1 if this is a daemon instance (not a node)
staking=0 #<-keep this =0
txindex=1
```
20) Ctrl + X and it will ask you to save file, hit Y

21) type `opioidd` (with no errors you should get Opioid Server Running)

22) if you have watch installed type "`watch opioidd getinfo`" and let it sync to the highest block.  
** you can simply type "`opioidd getinfo`" and wait for enough peers to connect **

Thank you,  
[OID Team](https://oid.life/)
