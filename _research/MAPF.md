---
layout: archive
title: "Multi-Agent Path Finding for Automated Warehouse"
permalink: /research/MAPF
author_profile: true
---

{% include base_path %}

<img src="https://bshen95.github.io/bojieshen.me/images/MAPF.gif" title="MAPF demo" style="float:right;width:290pt;height:200pt; padding-left:10px;"  alt="MAPF demo"/>
In automated warehouses, hundreds of robots work together to pick and deliver items simultaneously. To facilitate coordination and synchronisation the problem is often discretised: the environment is mapped onto a 4-connected grid, time is discretised into unit-sized steps and during each timestep robots can only move to an adjacent grid node or wait in their current location. Each individual robot aims to complete its task as quickly as possible, and therefore prefers the shortest path possible. But the robots must also work together, such that there is no collision between robots during the execution of their tasks. A variety of additional considerations appear in such setups. For example, thousands of orders are received daily each of which is further broken down into multiple delivery tasks for robots; the system also needs to continuously synchronise the robots, correct their location, and re-plan their paths; all of this must also occur in real-time. Yet the core challenge can be stated much more simply and abstractly: find a set of paths to move each robot/agent from a fixed source to fixed destination, all while ensuring that: (i) no collisions occur with other agents or obstacles; (ii) the sum of individual path costs is minimised; and (iii) the entire plan is found as quickly as possible. 


## Cluster Heurisitic and Bypass
<img src="https://bojie-shen.com/images/CHBP.png" title="CHBP" style="float:left;width:250pt;padding-right:10px;" alt="CHBP"/>
Conflict-based Search (CBS) is a state-of-the-art algorithm for MAPF, which can be understood as a best-first search algorithm that routes each agent independently and then re-solves conflicts afterwards. In recent years, there has been massive advances in the efficiency and scalability of CBS. However, all the recent CBS gains come from reasoning over pairs of agents only, we propose a novel algorithm called [Cluster Heuristic and Bypasses (CHBP) [1]](https://bshen95.github.io/bojieshen.me/publications/Shen00CHS23), which overcomes this limitation by extending CBS heuristics to reason about more than two agents at every node. CHBP does this by exploiting mutex propagation, a successful pairwise reasoning technique, which we extend to clusters of more than two agents. CHBP derives stronger bounds for CBS and also generate new kinds of bypasses, where the assigned paths of some agents are replaced to reduce the number of conflicts. In a range of empirical results, CHBP shows substantial improvements for CBS, especially on dense maps.




## MAPF Tracker
<img src="https://bshen95.github.io/bojieshen.me/images/tracker.jpg" title="tracker" style="float:left;width:400pt;padding-right:10px;" alt="tracker"/>
MAPF is an important core problem for many new and emerging industrial applications. Many works appear on this topic each year, and a large number of substantial advancements and performance improvements have been reported. Yet measuring overall progress in MAPF is difficult: there are many potential competitors, and the computational burden for comprehensive experimentation is prohibitively large. Moreover, detailed data from past experimentation is usually unavailable. To overcome this issue, we introduce a new set of methodological and visualisation tools to facilitate comparisons between a wide range of MAPF methods. We then undertake a large set of experiments, with several currently leading optimal and suboptimal solvers, in an attempt to map the current Pareto frontier. Finally, we propose a new [online platform](https://tracker.pathfinding.ai) for the MAPF community to track and validate further gains and to improve visibility for and access to existing solvers. 
This work was also presented as a system demonstration at ICAPS 2023. For a full length manuscript, please visit [here](https://arxiv.org/abs/2305.08446).