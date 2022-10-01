## iNCSL-Wego Mini Scout Manual
Need to read this instruction before using the robot.
> ***Prerequisite***: You should know how to turn on the robot.

Robot's Info:
  1. Companion computer: Intel NUC.
  2. IMU:
  3. GPS:
  4. Radar:
  5. Camera: IntelRealsense D345i.
  6. OS: Ubuntu 20.04

## Usage
There are mainly 2 operation scenarios:
1. Localhost: We only need to work with the robot, no extra laptop or PC are needed. However, this operation requires a monitor (with HDMI cable), a mouse, and a keyboard.
> **Note**: These hardware requirements are needed to access the companion computer for setup and excecuting commands (ROS).

   * The procedure can be summarized as follows:
     - Turn on the robot, connect the monitor using HDMI cable, connect mouse and keyboard using USB port.
     - Open terminal, and type `localhost`
     - Type into the terminal `rosrun wego bringup_can2usb.bash`
       >**Note**: There should be nothing (no message, no error) after this command if this is the first time you run this command after turn on the robot.
     - Next, run the command `roslaunch wego run_all.launch rosbag_record:=true`, change to false if you don't want to record a rosbag file (default is `false`).
       >**Note**: Please refer to this [section](#understand-the-robot) to know how to modify and choose sensor from `run_all.launch`.
     - Unplug the HDMI cable, USB cable (keyboard and mouse), and start controlling the robot using RC controller.
     - After finishing the work, plugin the HDMI, keyboard, and mouse. Press `Ctrl + C` to stop the ROS and recording.
     - The recorded rosbag file will be saved in the folder `.ros`.
       >**Note**: This is a hidden folder.
2. Network (LAN): This case requies a laptop and a wifi router to access and do everything wirelessly (No hardware connection is needed).
   * This method is advance, so please contact me if you want to do it.

## Understand the Robot
1. RC Controller
   * SWA: No function.
   * SWB: On/off control
     - Up: Turn off control.
     - Middle: Turn on control.
     - Down: Turn off control.
   * SWC: Lighting control (LED in front of the robot)
     - Up: Blinking the light.
     - Middle: Turn on light.
     - Down: Turn off the light.
   * SWD: Speed
     - Up: Fast.
     - Down: Slow.

3. Launch files


2. ROS Topic
