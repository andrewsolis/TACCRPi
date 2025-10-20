# TACCRPi
Instructions for build RPi cluster

This guide is mostly what was used to set up the cluster:
https://glmdev.medium.com/building-a-raspberry-pi-cluster-784f0df9afbd

The head node has an SSD that is a shared resource, and all of the RPi's are connected to a network switch. If you need to briefly be on wifi disconnect and reconnect back to them once you are done using wifi.

Started from step 4, as the RPis were already configured, but make sure to fix any timing discrepencies as slurm will only work if all node are on the same time. This step and 5 will require you to briefly be on wifi to download packages.

In step 5, the file paths are outdated anywhere you see slurm-llnl it should just be slurm.
