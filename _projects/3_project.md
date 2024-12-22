---
layout: page
title: Household Robot
description: Simulation of a household robot
img: assets/img/robot_manip/open_cupboard.png
importance: 3
category: work
pseudocode: true
---
## MIT 6.4212 Robot Manipulation

Abstract - Through this work we explored the feasibility of an
iiwa robot performing household pick and place tasks within
a simulated environment. Tasks include opening cabinet doors,
retrieving an obscured cup, and placing it on a table while en-
suring collision-free motion. We use bi-RRT for pathfinding and
refine trajectories with kinematic optimization. A state machine
manages tasks dynamically, overcoming challenges like scene
randomness, IK sensitivity, and collision checking. The model
achieved a 70% success rate across trials, with failure modes
including robot singularities and final cup pose misalignment.
Future work aims to integrate vision-based grasping and explore
alternative trajectory planning methods for randomized objects.
The gripper object grasping pose was predefined to grab a
cup and bowl object from within a cupboard. Key challenges
include determining collision-free trajectory while adhering to
joint singularities and hydroelectric contact.

<div style="text-align: center; margin: 20px 0;">
    <video width="640" height="360" controls>
        <source src="/assets/video/robot_simulatio_w_captions.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</div>

For our robot environment, we used predefined grasp poses for the cup. The robot manipulator could grasp from 3 orientations at the lip and 1 at the handel as shown in the image below

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robot_manip/cup_with_poses.png" title="grasp pose" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

We defined a state machine to manage the robot's actions. Our robot contained the following actions, Wait 1 Second, Open Right Door, Open Left Door, Push Door, Move Base, Remove Bowl, Pick Cup, Take Cup Out, Place Cup, Go Home, and End state. The full state machine is shown below

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robot_manip/state_machine.jpg" title="state machine" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

To determine a collision-free trajectory for our robot manipulator, we used bi-directional RRT pathfinding. The RRT algorithm was used to find an optimal path from the robot's current position to the goal position. The path was then refined using a shortcutting method. The full pathfinding algorithm is shown below.

<pre class="pseudocode">
Algorithm: Bi-RRT Algorithm

Input: Initial state q_init, Goal state q_goal
Output: Path connecting q_init and q_goal

1. Initialize T_a ← {q_init}, T_b ← {q_goal}
2. While Valid Path Not Found:
     a. q_rand ← SampleRandomNode()
     b. q_near ← NearestNeighbor(T_a, q_rand)
     c. ValidityChecker(q_rand)
     d. [q_added, a] ← T_a.Extend(q_near, q_rand)
     e. T_b.Extend(q_near, q_a, rand)
     f. Swap T_a and T_b
     g. If PathFound(T_start, T_goal): Break
3. Return Path connecting q_init and q_goal
</pre>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robot_manip/robot_scene_front.png" title="environment front" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robot_manip/robot_scene_back.png" title="environment back" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robot_manip/goal.png" title="goal" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, we observe the front of our robot environment. The middle displays the back of the cabinet and objects inside. The right image displays the final goal state of the robot.
</div>


<div class="row justify-content-center">
    <div class="col-sm-8">
        {% include figure.liquid path="assets/img/robot_manip/place_cup.gif" title="Final Cup Placement" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

