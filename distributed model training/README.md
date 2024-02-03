# Distributed Model Training

### Horovod

Horovod for distributed deep learning, bringing model training time down, an existing training script can be scaled up to run on hundreds of GPUs.

Mainly used for LAN and a commercial cloud service. Although, there is no access to a network of other Horovod users who also borrow and lend their GPU resources.

The kit is essential, but there is no dynamic resource sharing between users. The environment variable HOROVOD_HOSTNAME is often used to specify the hostname or IP address of each machine in the cluster. Requires a central location to grab the current command and a ping utility to ensure horovod server uptime.

$ export HOROVOD_HOSTNAME=hostname_of_new_pc:port,hostname_of_existing_pc1:port,hostname_of_existing_pc2:port \
$ horovodrun -np <num_processes> python your_training_script.py

### BOINC

in progress.
