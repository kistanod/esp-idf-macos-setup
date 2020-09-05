## Explanation -- short version of what is offered [here](https://rainmaker.espressif.com/docs/get-started.html)

Rainmaker is pretty much a custom homekit for your custom esp32 devices.  
It allows you to put a new build and now have to reconnect the device to their network.
Otherwise, I could not find any important uses of that

## Installation

```bash
git clone https://github.com/espressif/esp-rainmaker.git
cd esp-rainmaker/cli
```
make sure you are still in the correct python environment provided by esp
```bash
which python # has to be not your local python
pip3 install -r requirements.txt
python rainmaker.py signup <email>
python rainmaker.py login
python rainmaker.py claim $YOURPORTHERE
```

Then you can go to your rainmaker project and build.  
You will get a QR code just like in [this](https://www.youtube.com/watch?v=Heo18HLgh9g) video.
