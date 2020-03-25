# DroneKit_MAVlink_SITL

## Preparation:
```
pip install future
```
DroneKit 
```
pip install dronekit
```
https://github.com/mavlink/mavlink
clone it as Download ZIP -> extract it -> go to MAVlink's directory -> ``` python mavgenerate.py ```

cygwin : a unix interface that you can use on Windows.
Open a cygwin terminal. This procedure initialize documents under Cygwin's \home. The path should be C:\cygwin\home\"user name"\ if you didn't change it during installation.
```
cd C:\cygwin\home\"user name"\ 
```
Open *.bashrc* with text editor like vi .

At the last line of *.bashrc*, add :
```
export PATH=$PATH:$HOME/ardupilot/Tools/autotest
```

MAVproxy : 
SITL : 
FlightGear : a 3-D viewer of your vehicle in SITL, it's good to see how a vehicle takes off and land rather than in 2-D dimension.

```
cd ~/ardupilot/ArduCopter
../Tools/autotest/sim_vehicle.py  -L KSFO --map --console
```
```
mode guided
arm throttle
takeoff 40

rc 3 1500
mode circle
param set circle_radius 2000

mode rtl
```

## Reference:
* https://ardupilot.org/dev/docs/sitl-native-on-windows.html
* https://mavlink.io/en/getting_started/generate_libraries.html
* https://blog.csdn.net/ybhuangfugui/article/details/82348692
