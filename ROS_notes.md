# ROS Cheatsheet 

*Peikun Guo, 2018.12*

Frequently used ROS command options collected from [ROS wiki](wiki.ros.org). 

## ROS File System

* Find ros package

  ```bash
  rospack find [package_name]
  ```

* roscd

  * rosls
  * roslog (If you have run some ros programs before)

## ROS nodes

* roscore: master  (rosout)
* rosnode
  * rosnode list
  * rosnode ping <name>
* rosrun: run a node from given package

## ROS topic

* rqt_graph
  * ```bash
    rosrun rqt_graph rqt_graph
    ```
  * `rqt_graph` creates a dynamic graph of what's going on in the system. rqt_graph is part of the `rqt` package. 

* rostopic -h

  * params: bw    echo  find  hz    info  list  pub   type 

* rostopic echo

  * `rostopic echo` shows the data published on a topic.

* rostopic list

  * `rostopic list` returns a list of all topics currently subscribed to and published.
  * `rostopic list -v` : verbose list of topics to publish to.

* rostopic pub

  * `rostopic pub [topic] [msg_type] [args]`
  * e.g. `rostopic pub -1 /turtle1/cmd_vel geometry_msgs/Twist -- '[2.0, 0.0, 0.0]' '[0.0, 0.0, 1.8]'`
  * `-1`: publish one message and exit 
  * (double-dash tells the option parser that none of the following arguments is an option. This is required in cases where your arguments have a leading dash `-`, like negative numbers.)
  * The arguments are actually in **YAML** syntax (write our own!)

Details for publishing:

![image-20181221172943338](/Users/peikunguo/Library/Application Support/typora-user-images/image-20181221172943338.png)

* rostopic hz
  * reports te rate at which data is published
* rqt_plot
  * `rosrun rqt_plot rqt_plot`
  * `rqt_plot` displays a scrolling time plot of the data published on topics. 
  * :hot_pepper::pushpin::sweat_drops::cow::beer:
    * ![image-20181221175432431](/Users/peikunguo/Library/Application Support/typora-user-images/image-20181221175432431.png)

## ROS Messages

Communication on topics happens by sending ROS messages between nodes. **The publisher and subscriber must send and receive the same type of message. A topic type is defined by the message type published on it.**

* type

  * `rostopic type [topic]`

  * `rosmsg show [messagetype]`: detailed types of a message

    * e.g. `rosmsg show geometry_msgs/Accel`


















