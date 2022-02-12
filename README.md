# Device Connection Check `v. 1.0.0`
Detect when USB or Wi-Fi is connected to a device and take screenshots of the screen with a report for what happened.



# Configuration
Have a drive named `C`, create a file called `dcc.hjs` and set below configurations as desired.

path to config file has to be as below in-order to be read by the program :
```
C:\dcc.hjs
```

# Parameters
Each line starts with a word which indicates what the values are for, then an equal sign, then the value. [Example](#an-example-of-dcchjs-file-content)
__________________
### Window position
Set Window position, value in x y **[default=2 2]**
```
loc=2 2
```
__________________
### Window size
Window size in width height **[default=15 3]**
```
size=15 3
```
__________________
### Save Path
Main path to save data inside. **[default=E]**

it will create another folder inside called System and hide it. 
you can set sub-folders aswell. eg./ `E:\Pictures\save-here`. 
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
Number of pictures to be taken when usb/wifi detected. **[default=30]**
```
freq=30
```
__________________
### Delay
Delay between screenshots in milliseconds **[default=5000]** (5000 = 5 seconds)

Best to have it above 1000 (1 second).

```
delay=5000
```
__________________
### Auto Delete Old Files
Delete data older than value set in days. **[default=30]**

set as 0 to never delete. 
```
delete_day=30
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
```
//to set location of window.
loc=100 50

size=10 2
path=E
freq=10
delay=1000
delete_day=10
```
