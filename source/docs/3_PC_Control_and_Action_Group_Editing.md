# 3. PC Control and Action Group Editing

<p id ="anther3.1"></p>

## 3.1 PC Software Introduction

### 3.1.1 Install the Serial Port Driver

1) Double-click [**02 PC Software Installation Package\01 Driver\ch341ser.exe**](https://drive.google.com/drive/folders/1qN7LtmMBUqRqhJRAbwXvCm2j593ODaK7?usp=sharing).

<img src="../_static/media/chapter_3/section_1/media/image1.png" class="common_img"  />

2) Click **Install**. After installation succeeds, a message appears indicating that the driver has been installed successfully.

<img src="../_static/media/chapter_3/section_1/media/image2.png" class="common_img"  />

### 3.1.2 Launch the Software

:::{Note}
**The PC software is portable and does not need installation. Install the driver on the PC before use.**
:::

1) Find the PC software [**02 PC Software Installation Package\02 PC Software\MiniHexa.exe**](https://drive.google.com/drive/folders/1mL_xzRC31Jd9fkhl4Ro52ILncmW3Jg3U?usp=sharing).

<img src="../_static/media/chapter_3/section_1/media/image3.png" class="common_img"  />

2) Switch the software language in the top-left corner of the interface as needed.

<img src="../_static/media/chapter_3/section_1/media/image4.png" class="common_img"  />

### 3.1.3 Device Connection

#### Preparation

:::{Note}
* **Before this step, make sure the factory APP program has been flashed to the ESP32 controller. This program supports both APP control and PC software control.**
* **miniHexa is preloaded with the factory program before shipment and can be powered on for direct operation. If another program has overwritten it, find the factory program in [03 PC Software Program Files](https://drive.google.com/drive/folders/16SWjUtvrDMPfkTLHSJdKKmKxgA4cDKFW?usp=sharing) and download it again. For the download method, see [3.1.5 APP Program Download Instructions (Optional)](#anther3.1.5).**
:::

1) Turn on the miniHexa power switch.

<img src="../_static/media/chapter_3/section_1/media/image5.jpeg" class="common_img"  />

* **Serial Port Connection**

1) After the robot powers on, connect miniHexa to the PC with a Type-C data cable.

<img src="../_static/media/chapter_3/section_1/media/image6.jpeg" class="common_img"  />

2) Open the PC software, then select the corresponding device port for connection.

<img src="../_static/media/chapter_3/section_1/media/image7.png" class="common_img"  />

3) Check that the red circular icon turns green. This indicates a successful connection.

<img src="../_static/media/chapter_3/section_1/media/image8.png" class="common_img"  />

* **Wi-Fi Connection**

:::{Note}
**To connect the robot in this way, prepare a hotspot before powering on the robot. A Wi-Fi router or mobile hotspot can be used. Set both the hotspot name and password to "hiwonder".**
:::

1) After the robot powers on, it automatically searches for and connects to the hotspot named **hiwonder** with the password **hiwonder**. Wait a moment, then connect the PC to the same hotspot.

<img src="../_static/media/chapter_3/section_1/media/image9.png" class="common_img"  />

2) After the hotspot connection succeeds, open the PC software and click **Scan**. The software automatically matches miniHexa.

<img src="../_static/media/chapter_3/section_1/media/image10.png" class="common_img"  />

3) After scanning is complete, the miniHexa device option appears in the option bar below. Select it, then click **Connect**.

<img src="../_static/media/chapter_3/section_1/media/image11.png" class="common_img"  />

4) Check that the red circular icon turns green and that the device IP shows the miniHexa IP address. This indicates a successful connection.

<img src="../_static/media/chapter_3/section_1/media/image12.png" class="common_img"  />

### 3.1.4 Feature Overview

The PC software interacts with miniHexa in three modes for different functions:

1) General Mode: controls miniHexa omnidirectional movement.

<img src="../_static/media/chapter_3/section_1/media/image13.png" class="common_img"  />

2) Attitude Mode: controls the posture and center of gravity of miniHexa.

<img src="../_static/media/chapter_3/section_1/media/image14.png" class="common_img"  />

3) Action Edit: adjusts miniHexa servo deviation and edits or downloads miniHexa action groups.

<img src="../_static/media/chapter_3/section_1/media/image15.png" class="common_img"  />

:::{Note}
**For details about Deviation Mode in the PC software, see [5.1 Arduino IDE Installation and Deviation Calibration\5.1.2 Deviation Calibration](https://drive.google.com/drive/folders/1_sjERc-lw-v9gUabl3QbM24jkGcvWKrN?usp=sharing). This section does not explain it further.**
:::

The **General Mode** and **Posture Control** modes in the PC software are introduced in [3.2 Omnidirectional Movement Control](#anther3.2) and [3.3 Posture Control](#anther3.3).

The **Action Edit** mode in the PC software is introduced in sections **3.4-3.7**.

<p id ="anther3.1.5"></p>

### 3.1.5 APP Program Download Instructions (Optional)

The miniHexa is factory-flashed with the APP program. Downloading other feature programs will overwrite the APP control function. To use this function again, download the program again.

1) Connect miniHexa to the PC with a Type-C data cable.

<img src="../_static/media/chapter_3/section_1/media/image6.jpeg" class="common_img"  />

2) Open [**03 PC Software Program Files\remote\remote.ino**](https://drive.google.com/drive/folders/1yruiHCUgS6uSqDsVWiONNdxExU9UQBUs?usp=sharing), which is in the same path as this document.

<img src="../_static/media/chapter_3/section_1/media/image16.png" class="common_img"  />

3) After the file opens, select the development board model shown below.

<img src="../_static/media/chapter_3/section_1/media/image17.png" class="common_img"  />

4) Click **Tools** in the menu bar, then select the corresponding ESP32 development board configuration shown below.

<img src="../_static/media/chapter_3/section_1/media/image18.png" class="common_img"  />

:::{Note}
**Make sure the development board configuration is modified before downloading the program.**
:::

5) Click **Compile** first, then click **Upload**. When the following screen appears in the output box at the bottom of the software after upload is complete, the program download is complete.

<img src="../_static/media/chapter_3/section_1/media/image19.png" class="common_img"  />

<p id ="anther3.2"></p>

## 3.2 Omnidirectional Movement Control

### 3.2.1 Omnidirectional Movement Overview

In **General Mode**, the miniHexa robot can move in any direction on the X-Y plane in a three-dimensional coordinate system, move in the positive or negative Z-axis direction, and rotate left or right in place.

<img src="../_static/media/chapter_3/section_2/media/image1.jpeg" class="common_img"  />

### 3.2.2 Interface Description

<img src="../_static/media/chapter_3/section_2/media/image2.png" class="common_img"  />

* **In-Place Rotation Control**

| **Icon** | **Function** |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_2/media/image3.png" class="common_img"  /> | Rotate the robot left in place |
|<img src="../_static/media/chapter_3/section_2/media/image4.png" class="common_img"  /> | Rotate the robot right in place |
|<img src="../_static/media/chapter_3/section_2/media/image5.png" class="common_img"  /> | Restore the robot to the attention pose |

* **2D Movement Control**

| **Icon** | **Function** |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_2/media/image6.png" class="common_img"  /> | Move the robot forward in the Y+ direction |
|<img src="../_static/media/chapter_3/section_2/media/image7.png" class="common_img"  /> | Move the robot backward in the Y- direction |
|<img src="../_static/media/chapter_3/section_2/media/image8.png" class="inline-icon"  /> | Move the robot left in the X- direction |
|<img src="../_static/media/chapter_3/section_2/media/image9.png" class="inline-icon"  /> | Move the robot right in the X+ direction |
|<img src="../_static/media/chapter_3/section_2/media/image10.png" class="inline-icon"  /> | Stop the robot immediately |
|<img src="../_static/media/chapter_3/section_2/media/image11.png" class="common_img"  /> | Control the robot to move at any heading from 0 to 360 degrees for omnidirectional movement |

* **Height Control**

| **Icon** | **Function** |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_2/media/image12.png" class="inline-icon"  /> | Control the standing height of the robot by moving along the Z-axis |

<p id ="anther3.3"></p>

## 3.3 Posture Control

### 3.3.1 Posture Control Overview

In **Posture Control** mode, the miniHexa robot can control its center of gravity and posture in a three-dimensional coordinate system.

<img src="../_static/media/chapter_3/section_3/media/image1.jpeg" class="common_img"  />

### 3.3.2 Interface Description

<img src="../_static/media/chapter_3/section_3/media/image2.png" class="common_img"  />

* **Reset**

| **Icon** | **Function** |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_3/media/image3.png" class="common_img"  /> | Restore the robot to the attention pose |

* **Center of Gravity Control**

When controlling the center of gravity, the robot stands still in place and keeps a level posture. Drag the joystick to shift the whole body in the specified direction. This is center of gravity translation.

| **Icon** | **Function** |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_3/media/image4.png" class="common_img"  /> | Control the robot to shift its center of gravity at any angle from 0 to 360 degrees while standing still |
|<img src="../_static/media/chapter_3/section_3/media/image5.png" class="inline-icon"  /> | Control the robot to shift its center of gravity along the Z-axis while standing still |

* **Posture Control**

When controlling posture, the robot stands still in place and keeps its center of gravity unchanged. Drag the joystick to rotate the whole body around any X, Y, or Z coordinate axis. This is posture twisting.

| **Icon** | **Function** |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_3/media/image6.png" class="common_img"  /> | Control the robot posture by rotating around the X/Y axes while standing still |
|<img src="../_static/media/chapter_3/section_3/media/image7.png" class="inline-icon"  /> | Control the robot posture by rotating around the Z-axis while standing still |

## 3.4 Action Group Download and Editing Feature Overview

### 3.4.1 Launch the Software

:::{Note}
**The PC software is portable and does not need installation. Install the [driver](https://drive.google.com/drive/folders/1qN7LtmMBUqRqhJRAbwXvCm2j593ODaK7?usp=sharing) on the PC before use.**
:::

1. Find the PC software [**MiniHexa.exe**](https://drive.google.com/drive/folders/1mL_xzRC31Jd9fkhl4Ro52ILncmW3Jg3U?usp=sharing).

<img src="../_static/media/chapter_3/section_4/media/image1.png" class="common_img"  />

2. Copy it to any folder, then double-click it to use it.

3. Switch the software language in the top-left corner of the interface as needed.

<img src="../_static/media/chapter_3/section_4/media/image2.png" class="common_img" />

### 3.4.2 Device Connection

:::{Note}
**This section uses serial port connection as an example. For the Wi-Fi connection method, see [3.1 PC Software Introduction](#anther3.1).**
:::

1) Turn on the miniHexa controller board switch.

<img src="../_static/media/chapter_3/section_4/media/image3.jpeg" class="common_img"  alt="08" />

2) Use a USB cable to connect the Type-C port on the core board.

<img src="../_static/media/chapter_3/section_4/media/image4.jpeg" class="common_img"  alt="11" />

3) Open the PC software, then select the corresponding device port.

<img src="../_static/media/chapter_3/section_4/media/image5.png" class="common_img"  />

4) Check that the red circular icon turns green. This indicates a successful connection.

<img src="../_static/media/chapter_3/section_4/media/image6.png" class="common_img"  />

5) Find **Action Edit** in the menu bar and click it to enter the mode.

<img src="../_static/media/chapter_3/section_4/media/image7.png" class="common_img"  />

### 3.4.3 Action Edit Feature Description

<img src="../_static/media/chapter_3/section_4/media/image8.png" class="common_img"  />

**1.Device Connection Status**

| Icon | Function |
|:---|:---|
|<img src="../_static/media/chapter_3/section_4/media/image9.png" class="inline-icon"  /> | Displays the device connection status. Green indicates a successful connection. Red indicates that the device is not connected or has disconnected, and the prompt **Wired Not Connected** appears. |

**2.Servo Control Area:**

The Servo Control Area displays the selected servo icons. Adjust the corresponding slider value to adjust the servo position.

<img src="../_static/media/chapter_3/section_4/media/image10.png" class="common_img"  />

| Icon | Function |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_4/media/image11.png" class="common_img"  /> | Indicates the servo ID number. ID 18 is used as an example here. |
|<img src="../_static/media/chapter_3/section_4/media/image12.png" class="common_img"  /> | Adjusts the servo position. The minimum value is 500, and the maximum value is 2500. |

**3.Action Group Detail List**

The Action Group Detail List shows the duration of each action in the current action group and the servo values in each action.

<img src="../_static/media/chapter_3/section_4/media/image13.png" class="common_img"  />

| Icon | Function |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_4/media/image14.png" class="inline-icon"  /> | Frame number of each action in an action group. |
|<img src="../_static/media/chapter_3/section_4/media/image15.png" class="inline-icon"  /> | Duration of the action, which is the time required to execute the action. |
|<img src="../_static/media/chapter_3/section_4/media/image16.png" class="inline-icon"  /> | Action value under the corresponding ID, which is the position value. |

**4.Action Group Settings Area**

| Icon | Function |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_4/media/image17.png" class="inline-icon"  /> | Action group number selection button. Click it to select a number from 0 to 254. |
|<img src="../_static/media/chapter_3/section_4/media/image18.png" class="inline-icon"  /> | Downloads the actions in the current list to the controller board. After download, the original actions in that action group are overwritten. |
|<img src="../_static/media/chapter_3/section_4/media/image19.png" class="inline-icon"  /> | Erases the actions in the currently selected action group. |
|<img src="../_static/media/chapter_3/section_4/media/image20.png" class="inline-icon"  /> | Use with caution. Erases all actions in action groups 0 to 254. |
|<img src="../_static/media/chapter_3/section_4/media/image21.png" class="inline-icon"  /> | Runs the action group with the selected number once. |
|<img src="../_static/media/chapter_3/section_4/media/image22.png" class="inline-icon"  /> | Stops the action group that is currently running. |
|<img src="../_static/media/chapter_3/section_4/media/image23.png" class="inline-icon"  /> | Adds the servo values in the Servo Control Area as an action to the last row of the Action Group Detail List. |
|<img src="../_static/media/chapter_3/section_4/media/image24.png" class="inline-icon"  /> | Deletes the selected action from the Action Group Detail List. |
|<img src="../_static/media/chapter_3/section_4/media/image25.png" class="inline-icon"  /> | Replaces the selected angle values in the Action Group Detail List.<br>The angle values are replaced with the servo values in the center Servo Control Area, and the action duration is replaced with the time set in **duration(ms)**. |
|<img src="../_static/media/chapter_3/section_4/media/image26.png" class="inline-icon"  /> | Inserts one action row above the selected action.<br>The action duration is the time set in **duration(ms)**, and the angle values are the servo values in the center Servo Control Area. |
|<img src="../_static/media/chapter_3/section_4/media/image27.png" class="inline-icon"  /> | Moves the selected frame in the Action Group Detail List up and swaps its execution order with the previous frame. |
|<img src="../_static/media/chapter_3/section_4/media/image28.png" class="inline-icon"  /> | Moves the selected frame in the Action Group Detail List down and swaps its execution order with the next frame. |
|<img src="../_static/media/chapter_3/section_4/media/image29.png" class="inline-icon"  /> | Opens an action group file saved in .rob format. For the provided action group files, see **2. Software\10. Action Group Files**. |
|<img src="../_static/media/chapter_3/section_4/media/image30.png" class="inline-icon"  /> | Saves the actions currently in the Action Group Detail List to a specified location. |
|<img src="../_static/media/chapter_3/section_4/media/image31.png" class="inline-icon"  /> | After one action group is opened, click the Integrate Action File button to continue opening another action group file and integrate the two action group files into a new action group. |
|<img src="../_static/media/chapter_3/section_4/media/image32.png" class="inline-icon"  /> | Click this button to run the actions in the Action Group Detail List once. If **Loop** is selected, the robot repeats the action. |
|<img src="../_static/media/chapter_3/section_4/media/image33.png" class="inline-icon"  /> | Duration of the selected frame in the current **Action Group Detail List** area. |
|<img src="../_static/media/chapter_3/section_4/media/image34.png" class="inline-icon"  /> | Total accumulated duration of all frames in the current **Action Group Detail List** area. |

**5.Deviation Settings Area**

The Servo Control Area displays the selected servo icons. Adjust the corresponding slider value to adjust the servo deviation.

| Icon | Function |
|:--:|:--:|
|<img src="../_static/media/chapter_3/section_4/media/image35.png" class="common_img"  /> | Reads the robot servo deviations. |
|<img src="../_static/media/chapter_3/section_4/media/image36.png" class="common_img"  /> | Downloads the current robot servo deviations to the controller board. After download, the original actions of all servos are overwritten. |
|<img src="../_static/media/chapter_3/section_4/media/image37.png" class="common_img"  /> | Restores all robot servos to the central position value of 1500. |

## 3.5 Action Group Download Tutorial

### 3.5.1 Objective

Download the reference sample action group file in [**2. Software\10. Action Group Files**](https://drive.google.com/drive/folders/1bR30Kn7b84IqUfwQ5Mr-kZmwecwTGkwo?usp=sharing) to miniHexa.

### 3.5.2 Action Download

1) Turn on the miniHexa switch.

<img src="../_static/media/chapter_3/section_5/media/image1.jpeg" class="common_img"  alt="08" />

2) Connect it to the PC with a USB cable.

<img src="../_static/media/chapter_3/section_5/media/image2.jpeg" class="common_img"  alt="11" />

3) Click to switch to the Action Edit area.

<img src="../_static/media/chapter_3/section_5/media/image3.png" class="common_img"  />

4. The following uses downloading Action Group 6 as an example. First change the action group number to 6. Make sure the download number matches the action group.

<img src="../_static/media/chapter_3/section_5/media/image14.png" class="common_img"  />

5. Click **Open Action Group**, select the corresponding action group path [**2. Software\10. Action Group Files**](https://drive.google.com/drive/folders/1bR30Kn7b84IqUfwQ5Mr-kZmwecwTGkwo?usp=sharing), select Action Group 6, then open it.

<img src="../_static/media/chapter_3/section_5/media/image15.png" class="common_img"  />

6. Click **Download** to download the action group to the miniHexa.


## 3.6 Action Editing

### 3.6.1 Objective

Create a **Wave** action group consisting of 9 actions.

:::{Note}
**The actions in this section are only examples and are intended to help quickly learn the Action Edit feature. To reference standard actions, go to the reference sample action group files in [2. Software\10. Action Group Files](https://drive.google.com/drive/folders/1bR30Kn7b84IqUfwQ5Mr-kZmwecwTGkwo?usp=sharing).**
:::

### 3.6.2 Action Implementation

1) Turn on the miniHexa switch.

<img src="../_static/media/chapter_3/section_5/media/image1.jpeg" class="common_img"  alt="08" />

2) Connect it to the PC with a USB cable.

<img src="../_static/media/chapter_3/section_5/media/image2.jpeg" class="common_img"  alt="11" />

3) Click to switch to the Action Edit area.

<img src="../_static/media/chapter_3/section_5/media/image3.png" class="common_img"  />

* **Action Editing**

1) Switch to the Action Edit area, open **No. 6 Obstacle Crossing**, and keep only the first action. This creates the first action.

<img src="../_static/media/chapter_3/section_5/media/image4.png" class="common_img"  />

2) Raise the robot's right leg. Slide the slider for servo ID 8 to the value shown below.

<img src="../_static/media/chapter_3/section_5/media/image5.png" class="common_img"  />

:::{Note}
**Hold down the left mouse button and quickly click the slider for fine adjustment.**
:::

3) Click **Add Action** to add the bent and extended action to the action list on the right.

<img src="../_static/media/chapter_3/section_5/media/image6.png" class="common_img"  />

4) Raise the lower part of the robot's right leg. Slide the slider for servo ID 9 to the value shown below, then add the action.

<img src="../_static/media/chapter_3/section_5/media/image7.png" class="common_img"  />

5) Lower the lower part of the robot's right leg to create the waving effect. Slide the slider for servo ID 9 to the value shown below, then add the action.

<img src="../_static/media/chapter_3/section_5/media/image8.png" class="common_img"  />

6) Repeat actions 3 and 4 twice.

<img src="../_static/media/chapter_3/section_5/media/image9.png" class="common_img"  />

7. Finally, return the mechanical leg to its initial position. Click the first action in the action list. The mechanical leg rotates back to its initial posture. Then click **Add Action**.

<img src="../_static/media/chapter_3/section_5/media/image10.png" class="common_img"  />

* **Action Download**

1) After the actions are edited, save the action locally for later debugging. Click **Save File**. In the pop-up window, enter the file name and number, which is named **20 Wave** in this example, then save it as shown below.

<img src="../_static/media/chapter_3/section_5/media/image11.png" class="common_img"  />

2) After the file is saved, download the action to the corresponding action group. Select action group number 20 on the right side of the interface, then click **Download**.

<img src="../_static/media/chapter_3/section_5/media/image12.png" class="common_img"  alt="IMG_256" />

3) After the download is complete, the interface also displays the **Download Complete** pop-up. Click **OK** to close it.

<img src="../_static/media/chapter_3/section_5/media/image13.png" class="common_img"  />

## 3.7 Integrating Action Files

### 3.7.1 Objective

Learn the miniHexa action file integration function and merge action groups.

### 3.7.2 Hands-on Practice

1) Turn on the miniHexa switch.

<img src="../_static/media/chapter_3/section_6/media/image1.jpeg" class="common_img"  alt="08" />

2) Connect it to the PC with a USB cable.

<img src="../_static/media/chapter_3/section_6/media/image2.jpeg" class="common_img"  alt="11" />

:::{Note}
**If the factory program is running on the core board, briefly press the K1 button on the servo controller once after power-on to switch the working mode. When the buzzer beeps twice, the robot enters PC software control mode and starts processing PC software control operations.**
:::

3) Open the PC software, connect the software serial port, click the **Integrate Action File** button in the Action Group Settings Area, and open Action Group 6 in [**2. Software\10. Action Group Files**](https://drive.google.com/drive/folders/1bR30Kn7b84IqUfwQ5Mr-kZmwecwTGkwo?usp=sharing).

<img src="../_static/media/chapter_3/section_6/media/image3.png" class="common_img"  />

4) The parameters of Action Group 6 are now displayed in the Action Group Detail List.

<img src="../_static/media/chapter_3/section_6/media/image4.png" class="common_img"  />

5) Click **Integrate Action File** again, then select Action Group 14 for integration.

<img src="../_static/media/chapter_3/section_6/media/image5.png" class="common_img"  />

<img src="../_static/media/chapter_3/section_6/media/image6.png" class="common_img"  />

6) Click the "<img src="../_static/media/chapter_3/section_6/media/image7.png" class="inline-icon" style="width:50px" />" button to run the newly integrated action group online once.

7) Click the **Save Action File** button to save the newly integrated action group for later debugging. This example names it **21**.

<img src="../_static/media/chapter_3/section_6/media/image8.png" class="common_img"  />

:::{Note}
**If too many actions are integrated in the Action Group Detail List, the PC software prompts that the limit has been exceeded. In this case, the action cannot be downloaded to the controller board and can only be run online for preview.**
:::

## 3.8 APP Custom Control

### 3.8.1 Objective

Use the custom control function in the mobile APP to execute the **20 Wave** action group file edited in **Action Editing Tutorial** in this unit.

### 3.8.2 Hands-on Practice

#### Preparation

1) Confirm that Bluetooth and location services are enabled on the phone.

2) Confirm that Action Group 20 has been downloaded to miniHexa successfully. The PC software displays a prompt after a successful download.

#### Operation Steps

1. Turn on the robot switch to power on the device.

2. Open the **Wonderbot** mobile APP and connect the device.

3. Tap **Action** on the main interface.

<img src="../_static/media/chapter_3/section_7/media/image1.png" class="common_img"  />

4. Tap **Add** in the pop-up interface.

<img src="../_static/media/chapter_3/section_7/media/image2.png" class="common_img"  />

5. In the pop-up interface, enter the action group name and action group number. The action name can be filled in freely, but the action group number must be correct. Otherwise, the action cannot be executed.

<img src="../_static/media/chapter_3/section_7/media/image3.png" class="common_img"  />

6. After adding is complete, tap **Action Group** again to open the Custom Action Group interface. Tap the action name button to execute it once.

<img src="../_static/media/chapter_3/section_7/media/image4.png" class="common_img"  />

7. To modify or delete it, long-press the action name button, then tap **Delete**.

<img src="../_static/media/chapter_3/section_7/media/image5.png" class="common_img"  />

