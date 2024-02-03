# Distributed Model Training

### Horovod

Horovod for distributed deep learning, bringing model training time down, an existing training script can be scaled up to run on hundreds of GPUs. In code distributed commands for TensorFlow, PyTorch, Apache MXNet framework.

Such as..

import horovod.tensorflow as hvd \
import horovod.torch as hvd

and

optimizer = hvd.DistributedOptimizer(optimizer)

Mainly used for LAN and a commercial cloud service. Although, there is no access to a network of other Horovod users who also borrow and lend their GPU resources.

The kit is essential, but there is no dynamic resource sharing between users. The environment variable HOROVOD_HOSTNAME is often used to specify the hostname or IP address of each machine in the cluster. 

To WAN servers over the internet...

1. Requires a central location for users to grab the current HOROVOD_HOSTNAME cluster command, relative to priority of your node in the network. The script generates the cluster HOROVOD_HOSTNAME export command depending on the specific callers uptime and contribution and places them with peers of their kind.
2. A ping, statistic utility to ensure horovod server uptime, grade servers.

$ export HOROVOD_HOSTNAME=hostname_of_new_pc:port,hostname_of_existing_pc1:port,hostname_of_existing_pc2:port \
$ horovodrun -np <num_processes> python your_training_script.py

### Apache Spark

Unified engine for large-scale data analytics. Data science at scale, erform Exploratory Data Analysis (EDA) on petabyte-scale data without having to resort to downsampling. Machine learning, train machine learning algorithms on a laptop and use the same code to scale to fault-tolerant clusters of thousands of machines.

$ wget https://www.apache.org/dyn/closer.lua/spark/spark-3.5.0/spark-3.5.0-bin-hadoop3.tgz \
$ sudo tar xvf spark-3.5.0-bin-hadoop3.tgz -C /usr/local/ \
$ sudo ln -s /usr/local/spark-3.5.0-bin-hadoop3/ /usr/local/spark \
$ echo 'export PATH=$PATH:/usr/local/spark/bin' >> ~/.bashrc \
$ source ~/.bashrc \
$ spark-shell --version

With Apache Spark is installed, ensure Java Development Kit (JDK) and Scala are correctly configured.

$ java -version \
$ scala -version

Involves setting up a master node, and then adding worker nodes. Test cluster functionality. Worker nodes can be over the internet. Jobs are sent to the master node for processing and the master node must rank worker nodes.

### BOINC

The guide to making a new BOINC project is here. https://boinc.berkeley.edu/trac/wiki/CreateProjectCookbook \
Ideally, someone would set up one project as a persistent server node and clients would submit their model training jobs to the server. The BOINC project was not really made for machine learning, the hack around.

1. Cluster management utility to map and grade the network.
2. Task scheduler, wait for submitted model training jobs.
3. Alteration of code to add tf.cluster information on tf.distribute.
4. Execute the script on the master node utilizing the cluster directly.

All nodes need to be on the same version of tensor and python and working.

### Other

Google Colab with Jupyter notebook environment, Kaggle Kernels offers something similar. 
