# TACCRPi
Instructions for build RPi cluster

This guide is mostly what was used to set up the cluster:
https://glmdev.medium.com/building-a-raspberry-pi-cluster-784f0df9afbd

The head node has an SSD that is a shared resource, and all of the RPi's are connected to a network switch. If you need to briefly be on wifi disconnect and reconnect back to them once you are done using wifi.

Started from step 4, as the RPis were already configured, but make sure to fix any timing discrepencies as slurm will only work if all node are on the same time. This step and 5 will require you to briefly be on wifi to download packages.

In step 5, the file paths are outdated anywhere you see slurm-llnl it should just be slurm.

In general, headnode should we the RPi with the most GB to prevent any bottlenecks for the cluster.

The nodes/models in the cluster:
Magnolia: RPi 3
headnode and child1: RPi 4

headnode is the master/head node for the cluster

unless updated: currently SSH is not working on child1

use sinfo on the headnode to check states of each node after loading:
  Down (cannot communicate properly for whatever reason)
  UNK (unknown) (means the the slurm controller failed to start on that node for whatever reason –usually outdated specs (need to comment out     unnecessary configurations for this to be fixed)
  Up (is working!)

They are all able to speak with each other through the switch so it is very important that:
- The switch is working and connected
- They are all connected to the switch






