#Heroku Command
###Add SSH Key on Heroku
- Genrate ssh key
```bash
$ssh-keygen -t rsa
```
- To see exiting attached key
```bash
$heroku keys
```
- Add ssh key
```bash
$heroku keys:add  // default place (~/.ssh/id_rsa.pub or ~/.ssh/id_dsa.pub). 
```
-Test SSH connection
```bash
$ssh -v git@heroku.com
```
-To remove key
```bash
$heroku keys:remove adam@workstation.local
```
