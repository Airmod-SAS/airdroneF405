# airdroneF405

## How to build 

```bash
sudo apt update && sudo apt upgrade
sudo apt -y install build-essential git curl clang-18 python3 python-is-python3
mkdir -p ~/workspace/airmod
cd ~/workspace/airmod
git clone https://github.com/betaflight/betaflight.git
cd betaflight
git checkout 4.5.2
make arm_sdk_install
rm -rf src/config/ && git clone https://github.com/airmod-sas/config.git -b add-airdronef405 src/config/
make AIRDRONEF405
```
