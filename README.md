# Pointcloud to Laserscan Nodelet

This ROS package launches a nodelet that converts pointcloud data to laser scan data. It is based on the code from [pointcloud_to_laserscan](https://github.com/ros-perception/pointcloud_to_laserscan) but improved in the sense that the max height of the point cloud is obtained dynamically taking into account the height og the robot.

## Launch File

The main launch file for this package is `sample_nodelet.launch`. Below is a brief description of its contents:

### Nodes

- `pointcloud_to_laserscan`: This nodelet is loaded into the sensor's nodelet manager. It converts pointcloud data to laser scan data.

### Parameters

- `target_frame`: The frame to which the scan should be transformed. Default is `camera_link`.
- `min_frame`: The frame corresponding to the minimum height of the robot. Default is `base_link`.
- `max_frame`: The frame corresponding to the maximum height of the robot. Default is `head2_link`.
- `transform_tolerance`: The tolerance for the transform. Default is `0.01`.
- `min_height`: The minimum height for the points to be considered. Default is `0.0`.
- `max_height`: The maximum height for the points to be considered if no frame is inserted on min_frame and max_frame. Default is `1.0`.
- `angle_min`: The minimum angle for the scan. Default is `-1.5708` (i.e., -π/2).
- `angle_max`: The maximum angle for the scan. Default is `1.5708` (i.e., π/2).
- `angle_increment`: The angle increment for the scan. Default is `0.0087` (i.e., π/360).
- `scan_time`: The time between scans. Default is `0.3333`.
- `range_min`: The minimum range for the scan. Default is `0.45`.
- `range_max`: The maximum range for the scan. Default is `4.0`.
- `use_inf`: Whether to use infinity for out-of-range values. Default is `true`.
- `inf_epsilon`: The epsilon value for infinity. Default is `1.0`.
- `concurrency_level`: The concurrency level for processing pointclouds. Default is `1`.

## Usage

To launch the nodelet, use the following command:

```bash
roslaunch pointcloud_to_laserscan sample_nodelet.launch
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.