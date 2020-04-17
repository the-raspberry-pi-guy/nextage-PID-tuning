# nextage-PID-tuning

Discussion with Vlad:
 * Set integral to 0
 * Observe with RQT Multiplot
 * Configure with RQT Configure

## Progress Log
* 16/04 - Got Gazebo working on home PC, imported the Nextage model and setup workspace ready for tuning.
  * Issues with Nvidia drivers on home PC. Ensure installed with Additional Drivers in Ubuntu
  * Source everything `. devel/src`
  * Run Nextage model in Gazebo with: `roslaunch nextagea_gazebo nextagea_world.launch`
  * Make sure all dependencies are installed with: `rosdep install --from-paths ./ -iy`

* 17/04
  * Great videos on PID control: https://www.youtube.com/watch?v=wkfEZmsQqiA, https://www.youtube.com/watch?v=NVLXCwc8HzM, https://www.youtube.com/watch?v=7dUVdrs1e18, https://www.youtube.com/watch?v=sFOEsA0Irjs
![](img/pid.png)