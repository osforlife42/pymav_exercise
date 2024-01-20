# pymav_exercise

## Purpose

The purpose of this exercise is to assess candidates' abilities in quickly learning robotic frameworks, designing robotic systems, and integrating them into a multi-robot system. Enjoy the challenge!

In this exercise, you will engage with the following topics:

1. Ardupilot basics - understanding ardupilot code, sitl, mission planner, mavlink, etc.
2. mavlink-python communication.
3. Networking and multirobot architecture and design.

## Prerequisites

1. An Ubuntu 18.04-20.04 computer with an online network connection (or necessary installations available, as per the tutorials).
2. Basic knowledge of Linux commands.

## Important Notices - For the Examiner's Eyes Only

1. This exercise focuses on testing the candidate's skills in learning and utilizing ardupilot concepts quickly. It includes all the necessary resources to run sitl and Mission Planner without devops issues on a Linux computer. Installations are required but should be no more complex than following an online tutorial. Docker knowledge is not a prerequisite. Stations at the offices need to be cleaned up to ensure they can run and install all relevant resources and programs.
2. The exercise evaluates the candidate's ability to learn ardupilot concepts, run Mission Planner, control a drone, and connect over pymavlink to control it.
3. It assesses the candidate's capability to understand and solve challenges in robotics systems, especially asynchronous data sources, data flows, and the quick integration of open-source packages and utilities.
4. The exercise checks the candidate's proficiency in designing and writing Python programs at a high standard. After completing the exercise, the examiner should assess the code's design and quality, asking questions to gauge a full understanding of the design and potential challenges on a larger scale.
5. Candidates should allocate 2 full days for this exercise.

## The Exercise in a Sentence

"Write a code that controls a drone and tracks another drone at a given height above it."

## Important Resources

1. Ardupilot Docs - [https://ardupilot.org/copter/index.html](https://ardupilot.org/copter/index.html)
2. SITL - [https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html](https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html)
3. Mavlink ICD - [http://mavlink.io/en/messages/common.html](http://mavlink.io/en/messages/common.html)
4. Mission Planner Docs - [https://ardupilot.org/planner/](https://ardupilot.org/planner/)
5. And Most Importantly - The Entire Internet! :)

## Exercise Flow

1. Read the following [tutorial](https://ardupilot.org/dev/docs/building-setup-linux.html#building-setup-linux) and this [one](https://ardupilot.org/dev/docs/building-setup-linux.html#building-setup-linux). Install and run a drone (copter) in sitl.
2. Install Mission Planner using this [tutorial](https://ardupilot.org/planner/docs/mission-planner-installation.html). Connect to sitl following this [tutorial](https://ardupilot.org/dev/docs/using-sitl-for-ardupilot-testing.html).
3. Use Mission Planner docs and tutorials to take off the drone in sitl, sending it to different points on the map.
4. Congratulations! You've successfully completed your first drone flight!
5. Now, let's make it more interesting. Write a Python program that connects to the vehicle via mavlink protocol, arms it, takes it off, and sends it to a given known location (lat, lon, alt). There are no limitations to the solution; feel free to use any framework of your liking to achieve the goal.
6. Cool! It's practically autonomous!
7. Now, add another drone to the game. Ensure you can control both drones independently using Mission Planner (one at a time, without each one influencing or interfering with the other). Both should be visible together on Mission Planner.
8. Here comes the fun part. Develop a program that connects to a drone and, using a configuration file, decides if this drone is the follower or the leader.
   - If it is the leader, send the current position of the drone to the other drone.
   - If it is the follower, receive the position of the leader and send the drone to this location.
   
   Design considerations:
   - These programs ideally run on an onboard computer next to the flight controller (simulated using sitl). They run on different computers and need to communicate somehow between them.
   - You may need to read several messages from the flight controller and simultaneously send commands to it. Your program and design should enable that.

9. **Surprise Surprise** (this segment should come after one day into the exercise) - make the follower and the leader switch their roles using a command line interface (CLI) command at runtime.

Hope you enjoyed!