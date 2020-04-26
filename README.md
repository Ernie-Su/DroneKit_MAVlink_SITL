# DroneKit_MAVlink_SITL

## Preparation:

### Future
```
pip install future
```
***

### SITL
```
pip install dronekit-sitl
```
***

### MAVproxy
A command line, powerful, light GCS(ground control station).
* Download [MAVproxy on Windows](http://firmware.ardupilot.org/Tools/MAVProxy/MAVProxySetup-latest.exe) and install it.
***

### DroneKit 
```
git clone https://github.com/dronekit/dronekit-python.git
cd ./dronekit-python
sudo python setup.py build
sudo python setup.py install
```
***

### MAVlink
1. Go to https://github.com/mavlink/mavlink
2. clone it as Download ZIP and extract it. Go to MAVlink's directory.
3. ```python mavgenerate.py```
***

### Cygwin
It's a unix interface that you can use on Windows.
1. Open a cygwin terminal. This procedure initialize documents under Cygwin's \home. The path should be C:\cygwin\home\username\ if you didn't change it during installation.
2. ```cd C:\cygwin\home\username\```
3. Open *.bashrc* with text editor like vi. At the last line of *.bashrc*, add :
```
export PATH=$PATH:$HOME/ardupilot/Tools/autotest
```
***

## Start Simulation :
Before we connect to UAV, we can try some simulations using SITL(Software in the Loop). 

The following is the method to start your STIL simulation.

```
cd ~/ardupilot/ArduCopter
../Tools/autotest/sim_vehicle.py  -L KSFO --map --console
```

These are some example commands to make a copter completes a whole mission.

```
mode guided
arm throttle
takeoff 40

rc 3 1500
mode circle
param set circle_radius 2000

mode rtl
```
***

## Connect to UAV : 
Let's connect to our UAV through MAVproxy.
1. Open cmd and ```cd C:\Users\User\AppData\Local\MAVProxy```
2. ```mavproxy.py --master="com3"```
3. It'll connect to your drone over USB port. You can also connect over Network(IP address). I use *com3* to connect with my drone.
4. By default, the logfile will be saved as mav.tlog and mav.tlog.raw in the same folder that MAVProxy was executed from.

Before you enter commands, make sure you have already **taken the propellers off** for safety reasons.

* You can try some easy command like ```arm throttle``` and ```takeoff 1``` or ```disarm```
***

## Reference:
* MAVlink environment : https://blog.csdn.net/ybhuangfugui/article/details/82348692
* Simulation : https://dev.px4.io/v1.9.0/en/simulation/
* MAVproxy : https://ardupilot.github.io/MAVProxy/html/index.html
* SITL : https://ardupilot.org/dev/docs/sitl-native-on-windows.html
* SITL_Wiki : https://code.google.com/archive/p/ardupilot-mega-tw/wikis/SITL.wiki
* MAVproxy_SITL : https://ardupilot.org/dev/docs/copter-sitl-mavproxy-tutorial.html
* mavgen : https://mavlink.io/en/getting_started/generate_libraries.html
* HD Streaming : https://discuss.ardupilot.org/t/unlimited-range-hd-streaming-with-lte/48670/2
