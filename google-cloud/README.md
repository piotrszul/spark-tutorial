Running Spark ML on Google Cloud
---------------------------------

This part of the tutorial describes how to run a big data machine learning job on Google Cloud.


### Preparation

### Creating a cluster

We will create a Dataproc cluster named `test-cluster` based on `n1-himem-4` instances (4CPU cores) with one master node and 5 worker nodes (the type and number of instances are chosen to fit into the default quota of 24CPUs). 

We will also setup the initialisation action for the cluster to install python pandas package in each node.

Using the Dataproc UI create the cluster with the following settings:

![Create Cluster](https://piotrszul.github.io/spark-tutorial/images/create-cluster.png)

Make sure you also set the **Initialisation action** in the expandable section as shown below.

![Create Cluster Ex](https://piotrszul.github.io/spark-tutorial/images/create-cluster-ex.png)

### Submitting a job

Once the cluster is up and and running we can submit a 'PySpark' job to run our python genomics clustering script.

Using the Dataproc UI submit a job with the following settings:

![Submit Job](https://piotrszul.github.io/spark-tutorial/images/submit-job.png)


You can track progress of the job at the console. It should take about 10 minutes to complete.

The final results should be similar to the following:

![Job Result](https://piotrszul.github.io/spark-tutorial/images/job-result.png)


### Downloading the results

_Note:_

_Please remeber to 'Delete' the cluster after you have finished running your jobs. If you keep it active you will be charged for the cloud usage even if you do not run any jobs!_

![Submit Job](https://piotrszul.github.io/spark-tutorial/images/cluster-list.png)





