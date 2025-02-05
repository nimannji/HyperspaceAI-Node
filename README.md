# Hyperspace Node
## 1. Browser Node
### 1. Visit: https://node.hyper.space/
### 2. Switch the red button to green

![image](https://github.com/user-attachments/assets/727b0c1e-031b-4f5c-9bb6-60a4becaf19b)

### 3. Save your *PrivateKey*
You can import it later

![Screenshot_518](https://github.com/user-attachments/assets/3e08837d-1261-4873-b038-e7f86222d1b2)
![Screenshot_519](https://github.com/user-attachments/assets/67506c7d-9932-462c-a4d0-29f3992d7e4a)

#

## 2. Linux CLI Node (VPS)
* You can also check out [Official repository](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file) for more commands and info

### Installation
```
curl https://download.hyper.space/api/install | bash
```
```
source /root/.bashrc
```
### Create my.pem file
```
nano my.pem
```
* Then paste the private key you get in the browser part
* Then press `CTRL+O` to save the file, press Enter to make changes and Press `CTRL+X` to exit the editor 
### Start your node

* Create a screen ro run it in background for later
```
screen -S hyperspace
```
* Run node
```
aios-cli start
```
* To continue, minimize your screen using `CTRL+A+D`
* For turning back to the screen, first you should check the all screen name using `screen -ls` then using `screen -r screen_name`

### Config Node
* After use pressed `CTRL+A+D` in the previous part and returning to the main terminal you could use the following commands 
* Download a required model
```
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```
* Import your private key form `my.pem` file
```
aios-cli hive import-keys ./my.pem
```
* Set those keys as the preferred keys for this session
```
aios-cli hive login
```
* Make sure the model is registered
```
aios-cli hive connect
```
* This one is for selecting tier, The lowest tier is 5, which also the browser uses.
* if your vps has good hardware, you could higher tiers like 3 to to receive 2x points
```
aios-cli hive select-tier 5
```
```
aios-cli hive select-tier 3
```

### Check Points
* To check your current multiplier and points
```
aios-cli hive points
```

![Screenshot_514](https://github.com/user-attachments/assets/b840775e-6c58-4fe4-bd95-a5b876ba7de5)

* Sometimes this is not working. You could check your points in the browser too

# Usefull commands

* Stop node
```
aios-cli kill
```
* Shortcut for Start, Login and Connect to Hive commands, if you've stopped you node
```
aios-cli start --connect
```
* Update node
```
aios-cli version
```

