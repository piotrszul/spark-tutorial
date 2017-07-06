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
2. `Run All` the notebook - it should run without errors (the and the output should he like [this](https://piotrszul.github.io/spark-tutorial/databricks/0.1_Welcome.html)
3. Please, have a look through the notebook to familiarize yourself with the different ways of using the notebook to run python code, shell commands and visualize the results. 

To run the rest of the tutorial follow the steps above for other notebooks in the `notebooks` directory.








  
