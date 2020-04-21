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

* 18/04
  * Difficulties with rqt_multiplot seg faulting when trying to subscribe to /joint_states. Think I get the same position information from /rarm_controller/state wihtout the seg fault:
![](img/rqt_multiplot.png)
  * Finding rqt_multiplot very tempremental and often crashing - just keep to single plots. FIXED: Own misuse - use the message receipt time on the x axis, rather than the clock.
  * Bring up with Vlad the difference in topic names between running Gazebo and running Kawada simulator

* 20/04
  * Complete rqt_multiplot configuration (see config file) - plot desired and actual as per Vlad's instructions
  * Can find good values for RARM_JOINT0 and RARM_JOINT1, but when trying motion test on RARM_JOINT2, a lot of disturbance occurs:
![](img/disturbance.png)

* 21/04
  * Discovered that similar (worse) calibration issues occur in the Nextage Open (open source version of IPAB's Nextage): https://github.com/tork-a/rtmros_nextage
  * Currently exploring the PR2 robot