# **Indoor Navigation using ArUco Markers**
## <a name="_9ga512b2el5h"></a>Description.

In our current project, we've used Turtlebot, a highly adaptable robotic platform, to tackle the exciting challenge of autonomous indoor navigation. Central to our approach is using ArUco markers, a sophisticated yet cost-effective computer vision technology, which plays a pivotal role in enabling the robot's autonomous exploration within unfamiliar indoor environments. This innovative solution presents promising prospects for warehouse management.

## <a name="_w1ig0sl0aaz"></a><a name="_ddw2x2js8guw"></a>Timeline.
1. Installed Ubuntu 20.04
1. Installed ROS-Noetic using  <https://wiki.ros.org/noetic/Installation/Ubuntu>
1. Studied ROS using <http://wiki.ros.org/ROS/Tutorials>
1. Performed tasks on turtlesim
1. Studied Hector and Gmapping, and its implementation in turtlebot3 simulation on gazebo
   1. Turtlebot3 simulation using <https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/>
   1. SLAM simulation using <https://emanual.robotis.com/docs/en/platform/turtlebot3/slam/>
1. Studied OpenCV for camera calibration and aruco detection
   1. Camera Calibration <https://www.youtube.com/watch?v=JHeNger8B2E&ab_channel=AiPhile>
   1. Aruco detection and pose estimation <https://www.youtube.com/watch?v=mn-M6Qzx6SE&t=2s&ab_channel=AiPhile>
1. Installed docker for ROS-melodic
   1. Install Docker
      <https://docs.docker.com/engine/install/ubuntu/>
      <https://docs.docker.com/engine/install/linux-postinstall/>
   1. ROS-melodic installed  - TurtleBot2.zip
1. Gazebo simulation of autonomous navigation using aruco markers	
1. Implementation of code on hardware
1. Added Lidar usage for obstacle avoidance using <https://hackmd.io/@soham24/SJebiuww3>

## <a name="_mjez62lfwq1f"></a><a name="_z1ycn3mo7n7y"></a>Requirements.
Software:

- Ubuntu 20.04
- Python3
- ROS-Noetic
- Docker Image for ROS-Melodic [link to Turtlebot2.zip]
- OpenCV 4.8.x (Noetic)
- OpenCV 4.2.x (Melodic)
- { Optional } Gazebo simulation package 

Hardware:

- TurtleBot Burger Model [Kobuki]
- Webcam
- YdLidar

## <a name="_9xnafqf8j77j"></a>How to use the Project.
1. Make sure you have all the software installed and hardware at hand.
1. Create a catkin package in **both**, your docker container (ROS-melodic) as well as your main device (ROS-noetic)
   1. Go to `cd ~/catkin\_ws/src`
   1. Do `catkin\_create\_pkg indoor\_nav rospy turtlesim geometry\_msgs sensor\_msgs std\_msgs`
   1. Go back to `cd ~/catkin\_ws` 
   1. Do `catkin\_make`
1. Put lidar\_data.py code in your ROS-Noetic package and camera.py, MultiMatrix.npz, and navi.py code as well as a lidar\_data.txt file in your ROS-melodic package, and make these all executable files.
1. Make sure to change calib\_data\_path in camera.py to MultiMatrix.npz path. Also, change lidar\_data\_path in lidar.py to the relative path of lidar\_data.txt to your ROS-noetic terminal, and in navi.py to the relative path to your container.
1. Connect your TurtleBot to your device and run the following code in your container:
   1. `bash .devcontainer/post\_create\_commands.sh`
   1. `roslaunch turtlebot\_bringup minimal.launch`
1. In your ROS-noetic terminal, run the following code:
   1. `roscore`
   1. `rosrun lidar\_data.py`
1. In your container, run the following code:
   1. `roscore`
   1. `rosrun camera.py`
   1. `rosrun navi.py`

## <a name="_44z702ozcbnp"></a>Results.
![Circle](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/7886d773-05b7-4da4-b53d-359e388bd1bc)
![Follower](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/f5053ae6-de9c-4cb3-83d3-6f92bf7d8f5c)
![GoToGoal](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/1d305525-d19c-492e-ab37-73c582553eaf)
![spiral](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/bddc54fe-f938-4c2e-9e18-fbbafa4948e6)
![SLAM](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/80864bf2-750e-4c82-afd8-e83bd4d40c03)
![Callibration](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/49e69d38-7107-448e-8964-b4660f910c96)
![ArucoDetection](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/40dc7f21-98fd-468c-a645-b57c4b78094e)
![SimulationDetection](https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/79d9cac0-ecdb-48a3-aff2-be8a78987bdc)

https://github.com/ShantanuRenghe/Indoor-Navigation-IvLabs/assets/128238705/a4e8cb60-965c-4dd5-a204-07aa2006ca37
