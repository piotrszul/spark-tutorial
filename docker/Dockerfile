FROM jupyter/minimal-notebook:3.2

MAINTAINER Piotr Szul

USER root

# Spark dependencies
ENV APACHE_SPARK_VERSION 1.6.0

# Install necessary packages
RUN apt-get -y update && \
    apt-get install -y --no-install-recommends openjdk-7-jre-headless python-qt4 && \
    apt-get clean

# Download pre-compiled Apache Spark
RUN wget -qO - http://d3kbcqa49mib13.cloudfront.net/spark-${APACHE_SPARK_VERSION}-bin-hadoop2.6.tgz | tar -xz -C /usr/local/

RUN cd /usr/local && ln -s spark-${APACHE_SPARK_VERSION}-bin-hadoop2.6 spark

#Use unprivileged user provided by base image
USER jovyan

# Install Python 2 packages and kernel spec
RUN conda create --yes -p $CONDA_DIR/envs/python2 python=2.7 \
    'ipython=3.2*' \
    'pandas' \
    'matplotlib' \
    'scipy' \
    'scikit-learn' \
    pyzmq \
    pil \
    tornado \
    && conda clean -yt

RUN $CONDA_DIR/envs/python2/bin/python \
    $CONDA_DIR/envs/python2/bin/ipython \
    kernelspec install-self --user

#Install World cloud http://amueller.github.io/word_cloud/
RUN $CONDA_DIR/envs/python2/bin/pip install wordcloud

#Install Drag'n'Drop Pivot Tableshttps://github.com/nicolaskruchten/jupyter_pivottablejs
RUN $CONDA_DIR/envs/python2/bin/pip install pivottablejs

#Prepare environment
ENV SPARK_HOME /usr/local/spark
ENV PYSPARK_PYTHON=$CONDA_DIR/envs/python2/bin/python2.7
ENV PYSPARK_DRIVER_PYTHON=ipython
ENV PYSPARK_DRIVER_PYTHON_OPTS="notebook --no-browser"

#Ship some data for workshop
#COPY data $HOME/work/data/
#COPY 00_welcome.ipynb $HOME/work/

# Switch back to root so that supervisord runs under that user
#USER root

#COPY and ADD don't add as the current user https://github.com/docker/docker/issues/7390, https://github.com/docker/docker/pull/13600
RUN chown jovyan:jovyan $HOME/work -R

#SparkUI
EXPOSE 4040

COPY notebook.conf /etc/supervisor/conf.d/
