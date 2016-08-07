Mpaycoin integration/staging tree
================================

http://www.mpaycoin.com

Copyright (c) 2015-2016 Mpaycoin Developers

What is Mpaycoin?
----------------

Mpaycoin actually came from Multiwebpay Coin.We are hoping, it will be on of the leading payment option for online market or industry.Its new digital currency that enables instant payments to
anyone, anywhere in the world. Mpaycoin uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. Mpaycoin is also the name of the open source
software which enables the use of this currency.

Official Details
----------------
Mpaycoin Symbol: ₥
Algorithm:SHA256
Type:PoW
Coin name:Mpaycoin
Coin abbreviation:MPC
Address letter:M
Block reward:100 coins
Total coin supply:126530612 coins
Block halving:620000

Bounty for Mpaycoin:
1. Adding to any exchanger/trading Platform- 2000₥
2. Make Block Explorer-1000₥
3. Design and for any developing -500₥ to 5000₥
4. For any issue solving/promoting on forum/writing article- 10₥-200₥

Official website: mpaycoin.com
Github: github.com/multiwebpay/mpaycoin
Facebook:www.facebook.com/Mpaycoin-1642611006057110
Slack:mpaycoin.slack.com

For more information, as well as an immediately useable, binary version of
the Mpaycoin client software, see http://www.mpaycoin.com

License
-------

Mpaycoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Mpaycoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](https://bitcointalk.org/index.php?topic=1564880).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.md`) or are
controversial.

Building Manually
---------
#cd
#git clone https://github.com/multiwebpay/mpaycoin.git
#cd mpaycoin/src
#make –f makefile.unix USE_UPNP=-
#strip mpaycoind
#sudo cp mpaycoind /usr/bin
#cd /usr/bin
#./mpaycoind
(You need to put mpaycoin.conf file on .mpaycoin folder and start compile)
Just put below line on mpaycoin.conf file, rpc user and pass have to be unique, never share this with anyone

rpcuser=rpc_mpaycoin
rpcpassword=a0146122e50e1479f5adc494d
rpcallowip=127.0.0.1
rpcport=7878
listen=1
server=1
txindex=1
daemon=1

To check Status:
#cd /usr/bin
#./mpaycoind getinfo

To generate MPC Address:
#cd /usr/bin
#./mpaycoind getnewaddress

Building From Readymade Daemon for Linux
-------------
Its a easy solution for non coders for compiling Mpaycoin. Just need to follow below few steps:
#cd
#wget http://mpaycoin.com/mpaycoin-daemon-linux.tar.gz
#tar -xzvf mpaycoin-daemon-linux.tar.gz
#chmod +x mpaycoind
#sudo mv mpaycoind /usr/bin/
#cd /usr/bin/
#./mpaycoind
Add mpaycoin.conf on .mpaycoin folder and restart daemon
#./mpaycoind




Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test mpaycoin-qt.pro
    make -f Makefile.test
    ./mpaycoin-qt_test

Every pull request is built for both Windows and Linux on a dedicated server,
and unit and sanity tests are automatically run. The binaries produced may be
used for manual QA testing.

### Manual Quality Assurance (QA) Testing

Large changes should have a test plan, and should be tested by somebody other
than the developer who wrote the code.


