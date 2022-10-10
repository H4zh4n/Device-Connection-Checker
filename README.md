# ![Logo](https://i.imgur.com/nSdZyTf.png) Device Connection Checker `v. 1.0.6`
Detect when USB or Wi-Fi is connected to a device and take screenshots with a report for what happened.
- Report for USB contains time of connection, drive letter.
- Report for Wi-Fi contains list of All Wi-Fi connected with their password.


# Interface
The app has three indicators (three states) :
### ![Blue](https://i.imgur.com/KSibZiU.png) ![Red](https://i.imgur.com/zHLwnn5.png) Blue/Red [Most left Indicator]

has two states (colors), blue and red.

- ![Blue](https://i.imgur.com/KSibZiU.png) If the color is blue, it means that when the app first ran, no screenshots were taken for today.
- ![Red](https://i.imgur.com/zHLwnn5.png) if it's red, it means that when the app started, there were already screenshots taken for today.

This is useful for when you have the app to run at startup. when it first runs, it will be blue when there are no screenshots taken. If we assume a wifi or usb was connected and screenshots were taken, now when the computer is restarted and the app runs second time, you'll see the first left bar as red, indicating that before the restart there were screenshots taken for today.

### ![Orange](https://i.imgur.com/QMmap0Y.png) Orange
Indicates a wifi connection occurred. everytime it blinks it's taking a screenshot.

### ![Green](https://i.imgur.com/esmtuzr.png) Green
Indicates a usb device was connected. also everytime it blinks it's taking a screenshot.

> The indicator colors can be changed through the config file. refer to color customization [here](#change-indicator-color).

# Configuration
To Customize different parameters, you must have a drive named `C`. create a file and name it `dcc.hjs` and set below configurations as desired.

path to config file has to be as below in-order to be read by the program :
```
C:\dcc.hjs
```

![path to config file](https://user-images.githubusercontent.com/47919702/194626608-7db2f2fd-dcde-4cba-8c5c-b1afe0879817.png)

# Parameters
Each line starts with a **_word_** which indicates what the values are for, then an **_equal sign_**, then the **_value_**. [Example](#an-example-of-dcchjs-file-content)
__________________
### Window position
To change (shift) location of the bars, use `loc` followed by two numbers seperated with space which represent x and y **[default=2 2]**
```
loc=2 2
```
__________________
### Window size
To resize bars use `size` followed by two numbers which represent width and height **[default=15 3]**
```
size=15 3
```
__________________
### Save Path
To change drive which to save data on, use `path` followed by a letter or full path. **[default=E]**

The program will create another folder inside your path called **System** and hide it. 
you can set sub-folders in path aswell. eg./ `E:\Pictures\save-here`. 
if sub-directors (after drive) don't exist the program will create them.

```
path=E:\sus\
```
OR EVEN
```
path=E
```

__________________
### Pictures Frequency
To change the number of screenshots taken when wifi or usb connected, use `freq` followed by a number which represents number of screenshots to take. **[default=30]**
```
freq=30
```
__________________
### Delay
To change delay between screenshots, use `delay` followed by a number which represents number of milliseconds between each screenshots (5000 = 5 seconds). not recommened to have value below 1000, make sure to do tests and see if it works for you if you set value below 1000. **[default=5000]**

```
delay=5000
```
__________________
### Auto Delete Old Files
To delete data/folders older than a certain day old use `delete_day` followed by a number which reperesents days. folders created number of days older than this value specified will be deleted when the program runs. set as 0 to never delete.  **[default=30]**

```
delete_day=30
```

a heads-up for someone using the program 5,883,516 years in the future, value of 0 actually sets day as max integer allowed, which is [2,147,483,647].
__________________
### Change Indicator color ![Green](https://i.imgur.com/esmtuzr.png) ![Orange](https://i.imgur.com/QMmap0Y.png) ![Blue](https://i.imgur.com/KSibZiU.png) ![Red](https://i.imgur.com/zHLwnn5.png) 
To change USB/WiFi indicator colors or Normal/Detected state colors use the following commands followed by a hex of the color (not case sensitive).

![Green](https://i.imgur.com/esmtuzr.png) Change USB Indicator color **[default=#2ECC71]** :
```
usb_color=#27AE60
```

![Orange](https://i.imgur.com/QMmap0Y.png) Change WiFi indicator color **[default=#E67E22]** : 
```
wifi_color=#8E44AD
```

![Blue](https://i.imgur.com/KSibZiU.png) Change Normal state color (not detected on app start-up) **[default=#34B9DF]** :
```
normal_color=#1ABC9C
```

![Red](https://i.imgur.com/zHLwnn5.png) Change Detected state color (detected on app start-up) **[default=#E74C3C]** :
```
detected_color=#C0392B
```

__________________
### Comments
To write comments in the `dcc.hjs` file use // or # infront of the line.
```
// This is a comment line.
# hey this is a comment line too.
```
__________________

# An Example of `dcc.hjs` file content
As a Note : If you didn't want to customize a part of the app and you were satisified with it, don't provide the command for it in the `dcc.hjs` file.

(don't forget the = {equal} sign between keywords and values)

```
//to set x, y location of window.
loc=100 50

# set width and height of bars
size=10 2

# Path of screenshots/reports (set as Drive E, Automatically creates a folder named System in it).
path=E

freq=10
delay=1000
delete_day=10
usb_color=#27ae60
normal_color=#1abc9c
```
