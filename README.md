# What is Unita?

Unita is an enterprise blockchain solution. It's featured of high TPS (Transactions Per Second) and low transaction confirmation time, to make DApps (Decentralized Applications) applicable to more business scenarios. Meanwhile, by using a consensus algorithm named [SCAR](https://doc.unita.network/en/SCAR-Consensus/) (Scalable Consensus Algorithm), storage and network consumption are minimized, so as to reduce operating costs. It’s developed on the basis of the open-source project, [Qtum](https://github.com/qtumproject/qtum), which is compatible with the Bitcoin UTXO data structure and Ethereum Solidity smart contracts.

# Resource
Tool: [Homepage](https://unita.network), [Stats](https://stats.unita.network), [Explorer](https://explorer.unita.network), [Faucet](https://faucet.unita.network), [One-click Blockchain](https://chain.unita.network).

Document: [English](https://doc.unita.network/en/), [中文](https://doc.unita.network/zh/).

# Quickstart
Please refer to: [English](https://doc.unita.network/en/Unita-Quick-Start/), [中文](https://doc.unita.network/zh/Unita-Quick-Start/).

# Build the source
## Build on Ubuntu
```
# Install dependencies
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

# Dependencies for the Qt GUI
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler qrencode

# Download the source code
git clone --recursive https://github.com/UnitaNetwork/unita
cd unita

# Build
./autogen.sh
./configure 
make

# Run
./src/unitad
./src/unita-cli help
# or the Qt GUI
./src/qt/unita-qt
```

## Build on CentOS
```
# Compile boost manually
sudo yum install python-devel bzip2-devel
git clone https://github.com/boostorg/boost.git
cd boost
git checkout boost-1.66.0
git submodule update --init --recursive
./bootstrap.sh --prefix=/usr --libdir=/usr/lib64
./b2 headers
sudo ./b2 -j4 install

# Install dependencies
sudo yum install epel-release
sudo yum install libtool libdb4-cxx-devel openssl-devel libevent-devel

# Dependencies for the Qt GUI
sudo yum install qt5-qttools-devel protobuf-devel qrencode-devel

# Download the source code
git clone --recursive https://github.com/UnitaNetwork/unita
cd unita

# Build
./autogen.sh
./configure 
make

# Run
./src/unitad
./src/unita-cli help
# or the Qt GUI
./src/qt/unita-qt
```

## Build on OSX
```
# Install the OS X command line tools
xcode-select --install

# Install Homebrew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# Install dependencies
brew install cmake automake berkeley-db4 libtool boost --c++11 --without-single --without-static miniupnpc openssl pkg-config protobuf qt5 libevent imagemagick --with-librsvg qrencode

# Download the source code
git clone --recursive https://github.com/UnitaNetwork/unita
cd unita

# Build
./autogen.sh
./configure 
make

# Run
./src/unitad
./src/unita-cli help
# or the Qt GUI
./src/qt/unita-qt
```