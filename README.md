Tutorial and examples for using Apache Spark
=============================================


This repository contains jupyter notebooks and examples data-sets for my Apache Spark tutorial.


### Prerequisites

### Running on Databricks Community Platform.

The easiest to run the examples is to use the [Databricks Platform](https://databricks.com/), which provides a cloud based analytics platform  for data science and  engineering. Databricks was founded by the team who created Apache Spark, and works with the works with the open source community to continue to expand the project.

In addition to the commercial platform Databrick offers a **free** [Community Edition](https://databricks.com/product/faq/community-edition), which is a great way to learn both Apache Spark and the Databricks platform and to run this tutorial.

To sign up for a **free** account go to: <https://community.cloud.databricks.com/>

To learn how to use Databricsk platform please familiarize yourself with the [Getting Started](https://docs.databricks.com/user-guide/getting-started.html) guide. 

You may also like to check out some of the featured notebooks, for example  [Introduction to Apache Spark on Databricks](https://docs.databricks.com/_static/notebooks/gentle-introduction-to-apache-spark.html)

If it seems a bit complicated, do not panic - we well cover the basic at the workshop.

To setup the Databricks platform to the tutorial:

1. In your workspace create a Folder named `spark-tutorial`
2. Import to `spark-tutorial` the notebook from this url: <https://raw.githubusercontent.com/piotrszul/spark-tutorial/master/setup/0.1_Setup_DataBricks.ipynb>  (or from the file in `setup/0.1_Setup_DataBricks.ipynb`) 
3. `Run All` the notebooks with the default cluster `MyCluster` - it should run without errors
4. `Restart` `MyCluster`

To verify that the setup if correct and run you first tutorial notebook:

1. Import to `spark-tutorial` the notebook from this url: <https://raw.githubusercontent.com/piotrszul/spark-tutorial/master/notebooks/0.1_Welcome.ipynb> (or from the file in `notebooks/0.1_Welcome.ipynb) 
2. `Run All` the notebook - it should run without errors (the and the output should be like [this](https://piotrszul.github.io/spark-tutorial/databricks/0.1_Welcome.html)
3. Please, have a look through the notebook to familiarize yourself with the different ways of using the notebook to run python code, shell commands and visualize the results. 

To run the rest of the tutorial follow the steps above for other notebooks in the `notebooks` directory.

### Running local with Docker

You can also run the tutorial notebooks on your computer with the  [Docker Platform](https://www.docker.com/what-docker).

First you need to install Docker Community Edition for you computer and OS from <https://www.docker.com>

Once the installation is successful you need to download the Docker image with the tutorial to your machine.

_WARNING: The image size is about 5GB so you will need to have at least that amount of free disk space. The download size is also a few giga bytes so be mindful of our Internet usage and the time it may take to finish._

To download the image at the command prompt type:

    docker pull piotrszul/spark-tutorial
       
Once the download is complete you can start your local pyspark enabled jupyter notebook with:

    docker run -it  -p 8888:8888  piotrszul/spark-tutorial

If all is good this should give you the following output:
    
    [I 02:41:57.564 NotebookApp] Writing notebook server cookie secret to /home/jovyan/.local/share/jupyter/runtime/notebook_cookie_secret
    [W 02:41:57.895 NotebookApp] WARNING: The notebook server is listening on all IP addresses and not using encryption. This is not recommended.
    [W 02:41:57.896 NotebookApp] WARNING: The notebook server is listening on all IP addresses and not using authentication. This is highly insecure and not recommended.
    [I 02:41:57.903 NotebookApp] Serving notebooks from local directory: /home/jovyan/spark-tutorial/notebooks
    [I 02:41:57.903 NotebookApp] 0 active kernels 
    [I 02:41:57.903 NotebookApp] The Jupyter Notebook is running at: http://[all ip addresses on your system]:8888/
    [I 02:41:57.903 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).

You can navigate your browser not to: <http://localhost:8888/> to see the list of available tutorial notebooks.

1. Open the `0.1_Welcome.ipynb` and run all the cells with `Cell\Run All` - it should run without errors (the and the output should be like [this](https://piotrszul.github.io/spark-tutorial/notebooks/0.1_Welcome.html)
2. Please, have a look through the notebook to familiarize yourself with the different ways of using the notebook to run python code, shell commands and visualize the results.

<font color='red'>IMPORTANT:</font> 

When you are done with the notebook close it with `File\Close and Halt`. Only one pyspark notebook may be running at any given time.

To stop the `jupyter` server press `[Ctrl+C]` twice at the console window.

You can start it again at any time with the `docker run ...` command above.

_NOTE: Every time you use  `docker run ...`  the server will start from the clean image, without any changes that you might have made. If you want to preserve your changes use the --name option when you run the server for the first time and then `start` command to connect to it, e.g.: _

    # run a server (container) named `my-server` for the first time:
    
    docker run -it  -p 8888:8888 --name 'my-server' piotrszul/spark-tutorial 
    
    # do some work and stop the server
    # to start `my-server` again use: 
    
    docker start -i 'my-server'
    
_NOTE: Please not that the  `piotrszul/spark-tutorial` image is under active development so please make sure you update is on the day of the workshop. The update is incremental so the download size will be small)_

 











    










  
