# airdroneF405

Current documentation made for Ubuntu environment

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

## How to configure

### install Betaflight-configurator

```bash
cd ~/workspace/airmod/
wget https://github.com/betaflight/betaflight-configurator/releases/download/10.10.0/betaflight-configurator_10.10.0_linux64-portable.zip
unzip betaflight-configurator_10.10.0_linux64-portable.zip
```

### run Betaflight-configurator

```bash
cd ~/workspace/airmod/Betaflight\ Configurator/
./betaflight-configurator
```

### load preset

some preset have been defined to simplify the configuration

- copy the _AIRDRONEF405_PRESET.txt_ file from this repository
- run Betaflight configurator
- connect the board
- go to __Presets__ menu
- click on __Load backup__
- load _AIRDRONEF405_PRESET.txt_