# nodex
Shell script to install a [Nodex Masternode]() on a Linux server running Ubuntu 16.04.
***

## Installation
```
wget -q https://raw.githubusercontent.com/HashGravy/MN-Script/master/install_enox.sh
bash install_nodex.sh
```

***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the nodex Desktop Wallet.  
2. Go to **Help -> "Debug Window - Console"** and type *getaccountaddress MN1*
3. Send **10000** nodex to **MN1**. You need to send all 10000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. click **tools** and select **open masternodes configuration file** tab  
8. then fill your details in this format:  
* Alias: **MN1**  
* Address: **VPS_IP:11220**  
* Privkey: **Masternode Private Key**  
* TxHash: **First value from Step 6**  
* Output index:  **Second value from Step 6**
## After it should look like this:
```
MN1 127.0.0.2:11220 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0
```
***   
9. Close and open the wallet again.
10. Go to **Masternodes** -> **My Master Nodes** tab
11. If you don't see your masternode, click **Update**
12. Unlock your wallet if it is encrypted
13. Select your masternode and click on **Start**
14. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
nodex-cli masternode status
```
***

## Usage:
```
nodexd -daemon
nodex-cli getinfo
nodex-cli masternode status
nano  ~/.nodex/nodex.conf
```

***
