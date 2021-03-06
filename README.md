# BITalinoDataCollection

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

This script connects to a BITalino device via Bluetooth, get readings for 1 min for baseline, then plays a video and records the readings during the video.

*Note that this script currently can only be run on Linux systems*

## Dependencies
* [Python >2.7](https://www.python.org/downloads/) or [Anaconda](https://www.continuum.io/downloads)
* [NumPy](https://pypi.python.org/pypi/numpy)
* [pySerial](https://pypi.python.org/pypi/pyserial)
* [pyBluez](https://pypi.python.org/pypi/PyBluez/)
* [BitalinoAPI](https://github.com/BITalinoWorld/revolution-python-api)
* [Mplayer](http://www.mplayerhq.hu)

### To install Dependencies:

**For Python 2.7**

```sh
sudo apt-get install python python-dev python-pip bluez libbluetooth-dev ffmpeg mplayer
sudo pip install numpy pyserial pybluez bitalino
git clone https://github.com/BITalinoWorld/revolution-python-api.git
cd revolution-python-api
sudo python setup.py install
```
*(For pip2.7) Note that if your pip complains about `no module named _internal` or `no module named internal`:*

```sh
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
sudo python get-pip.py --force-reinstall
```

**For Python 3**
```sh
sudo apt-get install python3 python3-dev python3-pip bluez libbluetooth-dev ffmpeg mplayer
sudo pip3 install numpy pyserial pybluez bitalino
```

**Note that the official BITalino git repo is no longer maintaining BITalino3X, which I have included in this repo. (Thanks to [Gautam Sawala](https://github.com/gautamsawala) for this suggestion) Use Python 2 for best results**

## Arguments

### single.py - To record data with 1 BITalino device:

Run without flags to use default settings.

* `--mac-address [MAC Address of the device]`

    If '--mac-address' is not set, default MAC Address 20:16:12:21:98:56 will be used.

* `--channels [Comma seperated list of integers from 0 - 5, representing channels]`

    If '--channels' is not set, all channels 0,1,2,3,4,5 will be monitored

    Example: 0,2,3 to monitor channels A1, A3, A4

* `--sampling-rate [Sampling Rate in Hz]`

    If '--sampling-rate' is not set, default sampling rate of 100 Hz will be used.
 
    Sampling Rate can be 1, 10, 100 or 1000 Hz.

* `--video [Path to video file]`

    If '--video' flag is not set, the script will ask you for video during execution
    
* `--output (-o)`

   Sets the output filename
	
   If '--output' flag is not set, default output filename 'PyBitSignals_(MAC Address)\_(date)_(time)' will be used

* `--help (-h)`

    Show instructions.
    
### multiple.py - To record data with several BITalino devices:

Run without flags to use default settings.

* `--mac-addresses [MAC Addresses of the devices, in a comma seperated list]`

    If '--mac-addresses' is not set, default MAC Addresses 20:16:12:21:98:56,20:16:12:22:01:29 will be used.

* `--channels [Comma seperated list of integers from 0 - 5, representing channels]`

    If '--channels' is not set, all channels 0,1,2,3,4,5 will be monitored

    Example: 0,2,3 to monitor channels A1, A3, A4

* `--sampling-rate [Sampling Rate in Hz]`

    If '--sampling-rate' is not set, default sampling rate of 100 Hz will be used.
 
    Sampling Rate can be 1, 10, 100 or 1000 Hz.

* `--video [Path to video file]`

    If '--video' flag is not set, the script will ask you for video during execution

* `--help (-h)`

    Show instructions.

## Compatibility Note
**This python script has only been tested on Ubuntu MATE on Raspberry Pi 3 Model B**
