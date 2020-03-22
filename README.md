# DroneKit_MAVlink_SITL

## Preparation:
```pip install future
```
```pip install future
```
DroneKit 
```pip install dronekit
```
https://github.com/mavlink/mavlink
clone it as ZIP
下載“MAVlink代碼生成工具包” -> 解壓縮 -> 進入MAVlink路徑 -> 輸入命令 python mavgenerate.py


cygwin
打开Cygwin Termianl窗口。
该步骤会在Cygwin的home目录下初始化文件。如果你使用了默认设置，那么目录应该为 C:\cygwin\home\你的用户名\

前往C:\cygwin\home\你的用户名\ ，用文本编辑器打开.bashrc。

在.bashrc末尾加上
export PATH=$PATH:$HOME/ardupilot/Tools/autotest


MAVproxy
SITL
FlightGear

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
https://ardupilot.org/dev/docs/sitl-native-on-windows.html
https://mavlink.io/en/getting_started/generate_libraries.html
https://blog.csdn.net/ybhuangfugui/article/details/82348692
