# rtabmap_RGBD_camera

(R)eal(T)ime(A)ppereance(B)ased Mapping using depth camera. 
If you do not have rtabmap package, install it please.

### rtabmap-databaseViewer ~/mymap.db 
rtabmap-databasedViewer is a great tool to detect loop closures (using SURF) and construct occupancy grid in 2D or 3D depending on the application.

### How to?

If you don't have a catkin workspace defined, do the following

create a folder somewhere convenient
'''sh
mkdir -p catkin_ws
cd catkin_ws
mkdir src
cd src
catkin_init_workspace
cd ..
catkin_make
'''
Once you have catkin_ws 

'''sh
cd catkin_ws/src
git clone https://github.com/zvatansever/rtabmap_RGBD_camera
cd ..
catkin_make
source devel/setup.bash
roslaunch rtabmap_RGBD_camera mapping.launch
'''
Open a new terminal
'''sh
rosrun teleop_twist_keyboard teleop_twist_keyboard
'''
Drive the robot around the room at least two times to detect the loop closures.
Once you are done, a new file will appear named mymap.db
You can access it using
'''sh
cd catkin_ws/src/rtabmap_RGBD_camera
rtabmap-databaseViewer mymap.db
'''

