---
title: "Shiryu NAKANO"
bookCollapseSection: true
url: /posts/engineering/ros2/
---


## Odom msgからPoseだけ取り出すことができる

[nav_msgs/Odometry Documentation](https://docs.ros.org/en/noetic/api/nav_msgs/html/msg/Odometry.html)
- Raw Message Definition

```
# This represents an estimate of a position and velocity in free space.  
# The pose in this message should be specified in the coordinate frame given by header.frame_id.
# The twist in this message should be specified in the coordinate frame given by the child_frame_id
Header header
string child_frame_id
geometry_msgs/PoseWithCovariance pose
geometry_msgs/TwistWithCovariance twist
```


geometry_msgs/PoseWithCovariance poseは、
Pose型と、その共分散行列（不確かさ？）を含んでいる。

```
# This represents a pose in free space with uncertainty.
Pose pose

# Row-major representation of the 6x6 covariance matrix
# The orientation parameters use a fixed-axis representation.
# In order, the parameters are:
# (x, y, z, rotation about X axis, rotation about Y axis, rotation about Z axis)
float64[36] covariance
```

c.f. [geometry_msgs/PoseWithCovariance Documentation](https://docs.ros.org/en/noetic/api/geometry_msgs/html/msg/PoseWithCovariance.html)

[msg/Pose Documentation](https://docs.ros2.org/foxy/api/geometry_msgs/msg/Pose.html)
https://docs.ros2.org/foxy/api/geometry_msgs/msg/PoseStamped.html


- Raw Message Definition

```
# A representation of pose in free space, composed of position and orientation.
Point position
Quaternion orientation

```



