# Lunarium Coin
Shell script to install an [Lunarium Masternode](http://lunariumcoin.io/) on a Linux server running Ubuntu 16.04.

***
## Installation:  

wget -q https://raw.githubusercontent.com/LunariumCoin/Lunarium-MN-Install/master/lunarium_install.sh
bash lunarium_install.sh
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Lunarium Coin Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **10000** SLRC to **MN1**.  
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to **Masternodes** tab  
8. Click **Create** and fill the details:  
* Alias: **MN1**  
* Address: **VPS_IP:PORT**  
* Privkey: **Masternode Private Key**  
* TxHash: **First value from Step 6**  
* Output index:  **Second value from Step 6**  
* Reward address: leave blank  
* Reward %: leave blank  
9. Click **OK** to add the masternode  
10. Click **Start All**  

***

## Usage:  

For security reasons **Lunarium** is installed under **lunarium** user, hence you need to **su - lunarium** before checking:    

```
LUNARIUM_USER=lunarium #replace lunarium with the MN username you want to check

su - $LUNARIUM_USER
lunariumd masternode status
lunariumd getinfo
```  

Also, if you want to check/start/stop **Lunarium**, run one of the following commands as **root**:

```
LUNARIUM_USER=lunarium  #replace lunarium with the MN username you want to check  

systemctl status $LUNARIUM_USER #To check the service is running.  
systemctl start $LUNARIUM_USER #To start Lunarium service.  
systemctl stop $LUNARIUM_USER #To stop Lunarium service.  
systemctl is-enabled $LUNARIUM_USER #To check whetether Lunarium service is enabled on boot or not.  
```  

***

## Credits:

Based on a script by Zoldur (https://github.com/zoldur). Thanks!
