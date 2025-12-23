# Snort Installation Guide

This document provides step-by-step instructions for installing Snort IDS.

## Prerequisites
- Ubuntu 20.04 LTS
- Internet access
- Sudo privileges

## Installation Steps

sudo apt update
sudo apt install -y build-essential libpcap-dev libpcre3-dev libdumbnet-dev bison flex zlib1g-dev xz-utils libssl-dev

wget https://www.snort.org/downloads/snort/daq-2.0.7.tar.gz
tar -xvzf daq-2.0.7.tar.gz
cd daq-2.0.7
./configure
make
sudo make install

wget https://www.snort.org/downloads/snort/snort-2.9.20.tar.gz
tar -xvzf snort-2.9.20.tar.gz
cd snort-2.9.20
./configure --enable-sourcefire
make
sudo make install
snort -V
