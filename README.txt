## A collection of scripts to put Linux machines on ad-hoc mode and
##    exchange broadcast messages between them
##       tested on Ubuntu 16.04.1 LTS
##
##  Copyright (c) 2016, Autonomous Networks Research Group. All rights reserved.
##     Contributor: Bhaskar Krishnamachari
##     Read license file in main directory for more details


There are 4 bash scripts included here: adhoc, reg, bct, and bcl. 
They are described below.

* adhoc -- puts computer in adhoc mode; 
         usage example: adhoc 1 
            the number refers to node id, default essid="testnet"
            start each node on ad-hoc mode one after the other
            and be sure to give each a different id
         usage example: adhoc 1 dummynetwork
            this makes the essid of the network to be "dummynetwork"
         note that this script requires sudo access

* reg   --  turn off adhoc mode and go back to standard (managed) mode

* bct   --  send broadcast messages
          usage example: bct 1234 
            the number refers to the port number
            once this script is running, type text in the window 
            each line entered is sent as a broadcast message

* bcl   --  listen to broadcast messages
          usage example: bcl 1234 
            the number refers to the port number
            once this script is running, 
            each broadcast message shows up on the screen as text


Typical use of scripts: 
  adhoc 1 (on machine 1) 
  adhoc 2 (on machine 2)
  (can verify the above by pinging 192.168.100.2 from machine 1 and vice versa)
  
  bct 1234 (on machine 1)
  bcl 1234 (on machine 2)
  now type on the screen on machine 1 and see what you get on machine 2  

The scripts generalize to any number of machines, just be sure to run adhoc
  sequentially with different id numbers. Can run bct and bcl on all machines, 
  just make sure the same port number is used in all machines.  
 
           
