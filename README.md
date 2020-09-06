# Beginner's guide on setting up esp32 development environment

After a dozen of mistakes and trials, here's a complete guide on how to set up, build and flash your esp32 projects onto esp32 motherboard.

## Installation


Use the package manager [brew](https://brew.sh/) to install cmake ninja ccache.  
Brew will also install necessary XCode command line tools.

```bash
brew install cmake ninja ccache
```

Then clone the project in your workspace and run the installation scripts.  
I suggest using either bash or zsh because they do not cause any errors.


```bash
git clone -b v4.1 --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
./install.sh
. ./export.sh
```

After this step, you have now added all necessary environments to your $PATH. You can check that by running echo $PATH. **Please note that you need to run . ./export.sh every time you exit your terminal**


## Connection

Take your esp module and connect it to any usb port on the computer and run
```bash
ls /dev/cu.*
```
and you will see something like this
```bash
/dev/cu.Bluetooth-Incoming-Port	/dev/cu.usbserial-0001
```
the second one is yours

## Compiling the Project

```bash
cd $PATH/to/your/project
idf.py build
```

## Flashing and Monitoring
```bash
idf.py -p /dev/cu.usbserial-0001 flash
idf.py -p /dev/cu.usbserial-0001 monitor
```

## Fullclean
Make sure to run fullclean if your build returns an error
```bash
idf.py -p /dev/cu.usbserial-0001 fullclean
```
