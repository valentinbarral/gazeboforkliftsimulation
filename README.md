**NOTE:** This repository is related with the next scientific work:

**Barral, V.**; **Escudero, C.J.**; **García-Naya, J.A.**; **Maneiro-Catoira, R.** *NLOS Identification and Mitigation Using Low-Cost UWB Devices.* Sensors 2019, 19, 3464.[https://doi.org/10.3390/s19163464](https://doi.org/10.3390/s19163464)

If you use this code for your scientific activities, a citation is appreciated.

# README

This project contains the forklift, sensors and world models and several ```.launch``` files to start a Gazebo simulation. 

## Launch

To launch a single simulation:

```$ roslaunch gtec_gazeboforkliftsimulation forklift_gazebo_simulation.launch```

This launcher launches the next nodes:

- Gazebos node. The node that launches the Gazebo simulator. A parameter ```<arg name="gui" value="true"/>``` can be used to select if Gazebo GUI is showed or not.
- ```gazebo_guide``` from packet```gtec_gazebo2ros``` This node moves the vehicle according the rules set in a ```.xml``` file.
- ```gazebo2ros``` from packet ```gtec_gazebo2ros``` publish topics from Gazebo in ROS.
- ```genericrangingfixer``` publishes measurements from the UWB anchors.
- ```kfpos``` location algorithm that publishes the position estimations.

To launch a set of simulations without position estimation can be used:

```$ roslaunch gtec_gazeboforkliftsimulation forklift_gazebo_simulation_no_kfpos.launch```

In this case the ```kfpos``` node is not launched. Instead, the nodes ```gazebo_auto_guide``` and ```gazebo_restart_service``` are launched to repeat the simulation several times. 
