# airdroneF405

## How to build 

### Prepare the environement 
this should be done only once
```bash
sudo apt update && sudo apt upgrade
sudo apt -y install build-essential git curl clang-18 python3 python-is-python3
mkdir -p ~/workspace/airmod
cd ~/workspace/airmod
git clone https://github.com/betaflight/betaflight.git
cd betaflight
git checkout 4.5.2
make arm_sdk_install
rm -rf src/config/ && git clone https://github.com/Airmod-SAS/betaflight-config.git -b add-airdronef405 src/config/
```

### Compile with the latest sources
```bash
cd ~/workspace/airmod/betaflight
cd src/config
git fetch --prune
git pull
cd ../..
make AIRDRONEF405
```
