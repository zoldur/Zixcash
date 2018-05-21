# ZixCash
Shell script to install a [ZixCash Masternode](https://bitcointalk.org/index.php?topic=3462388) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/Zixcash/master/zixcash_install.sh
bash zixcash_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the ZixCash Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **10000** ZIX to **MN1**. You need to send all 10000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open ZixCash Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Select your MN and click on **Start Alias**
12. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
zixcash-cli masternode status
```
***

## Usage:
```
zixcash-cli mnsync status
zixcash-cli masternode status #This will tell you if the masternode is running
zixcash-cli getinfo
```
Also, if you want to check/start/stop **Zixcash**, run one of the following commands as **root**:

```
systemctl status Zixcash #To check if Zixcash service is running  
systemctl start Zixcash #To start Zixcash service  
systemctl stop Zixcash #To stop Zixcash service  
systemctl is-enabled Zixcash #To check if Zixcash service is enabled on boot  
```  
***

## Donations

Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
