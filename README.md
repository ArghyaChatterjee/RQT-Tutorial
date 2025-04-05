# RQT Tutorial
This repository is about RQT tutorial. 

### What is RQT?

**RQT** is a Qt-based framework for GUI development for ROS. It comes with several **plugins** that help visualize and manage nodes, topics, parameters, graphs, etc.

---

## Step 1: Install RQT and Plugins

Most RQT packages are already included in standard ROS 2 desktop installations, but you can manually install them if needed:

```bash
sudo apt update
sudo apt install ros-humble-rqt ros-humble-rqt-common-plugins
```

Replace `humble` with your ROS 2 distro if using a different one.

---

## Step 2: Launch a ROS 2 Demo

Let's start a demo node to generate some data.

```bash
ros2 run demo_nodes_cpp talker
```

In another terminal:

```bash
source /opt/ros/humble/setup.bash
rqt
```

---

## Step 3: Useful RQT Plugins

Once `rqt` opens, go to `Plugins` in the top menu. Here are a few must-know plugins:

### 1. **rqt_graph**

- **Path**: `Plugins` → `Introspection` → `Node Graph`
- Shows how nodes are interconnected and what topics are being published or subscribed.

### 2. **rqt_plot**

- **Path**: `Plugins` → `Visualization` → `Plot`
- Visualizes numeric data over time.
- Example: Plot `/turtle1/pose/x` when using turtlesim.

### 3. **rqt_console & rqt_logger_level**

- View log messages and change logger levels dynamically.
- Useful for debugging live systems.

### 4. **rqt_topic**

- **Path**: `Plugins` → `Topics` → `Topic Monitor`
- View topic names, types, and frequencies.

### 5. **rqt_reconfigure** *(Not available in ROS 2 by default)*

- Unlike ROS 1, dynamic reconfigure isn't fully supported in ROS 2 core yet.

### 6. **rqt_service_call**

- Call services directly from the GUI.

---

## Example: Visualize turtlesim topics

In one terminal:

```bash
ros2 run turtlesim turtlesim_node
```

In another:

```bash
ros2 run turtlesim turtle_teleop_key
```

Now launch `rqt` and explore:

- Use **rqt_graph** to see node-topic connections.
- Use **rqt_plot** to visualize `/turtle1/pose/x`.
- Use **rqt_topic** to see real-time topic data.

---

## Tips & Troubleshooting

- If RQT crashes: Run with `rqt --clear-config` to reset saved window layouts.
- Use `Ctrl+Shift+P` to open the plugin selector quickly.
- You can dock/undock and arrange panels freely.

---

## More RQT Plugins

Install extra plugins:

```bash
sudo apt install ros-humble-rqt-image-view ros-humble-rqt-tf-tree
```

Use `rqt_image_view` to visualize image topics, and `rqt_tf_tree` to inspect transforms.

---
