# TACCRPi
Instructions for build RPi cluster

This guide is mostly what was used to set up the cluster:
https://glmdev.medium.com/building-a-raspberry-pi-cluster-784f0df9afbd

The head node has an SSD that is a shared resource, and all of the RPi's are connected to a network switch. If you need to briefly be on wifi disconnect and reconnect back to them once you are done using wifi.

Started from step 4, as the RPis were already configured, but make sure to fix any timing discrepencies as slurm will only work if all node are on the same time. This step and 5 will require you to briefly be on wifi to download packages.

In step 5, the file paths are outdated anywhere you see slurm-llnl it should just be slurm.

In general, headnode should be the RPi with the most GB to prevent any bottlenecks for the cluster.

The nodes/models in the cluster:
Magnolia: RPi 3
headnode and child1: RPi 4

headnode is the master/head node for the cluster

unless updated: currently SSH is not working on child1

use sinfo on the headnode to check states of each node after loading:
- Down (cannot communicate properly for whatever reason)
- UNK (unknown) (means the the slurm controller failed to start on that node for whatever reason –usually outdated specs (need to comment out unnecessary configurations for this to be fixed)
- Up (is working!)

They are all able to speak with each other through the switch so it is very important that:
- The switch is working and connected
- They are all connected to the switch

When turning on the RPi's if powered down be sure to turn on the headnode first before any of the child nodes, as the switch will let you SSH only into the first one. You cannot go from child node to headnode, and ideally if the cluster is set up correctly all you need is access to the headnode to run any programs.

Any issues will likely be found within the log if you recieve UNK as a status of a node.


Additional Notes on the Cluster:
https://docs.google.com/document/d/1FT6gdIzOaJzvHghcUACNUJ_Gm2P_MlZ-jk7aBySbbWk/edit?tab=t.0
https://docs.google.com/document/d/1tIlaqHSHRgjeAkjinBBHICIGmNuOACMjjzf2yv3-izU/edit?tab=t.0



