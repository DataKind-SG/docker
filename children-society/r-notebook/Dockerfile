# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
FROM jupyter/minimal-notebook:9e056d61b7a5

MAINTAINER Jupyter Project <jupyter@googlegroups.com>

USER root

# R pre-requisites
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    fonts-dejavu \
    gfortran \
    gcc && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER $NB_USER

# R packages
RUN conda config --add channels r && \
    conda install --quiet --yes \
    'r-base=3.3.2' \
    'r-irkernel=0.7*' \
    'r-plyr=1.8*' \
    'r-devtools=1.12*' \
    'r-tidyverse=1.0*' \
    'r-shiny=0.14*' \
    'r-rmarkdown=1.2*' \
    'r-forecast=7.3*' \
    'r-rsqlite=1.1*' \
    'r-reshape2=1.4*' \
    'r-nycflights13=0.2*' \
    'r-caret=6.0*' \
    'r-rcurl=1.95*' \
    'r-crayon=1.3*' \
    'r-psych=1.6*' \
    'r-dplyr=0.5*' \
    'r-igraph=1.0*' \
    'r-tm=0.6*' \
    'r-magrittr=1.5' \
    'r-stringr=1.1*' \
    'r-shinydashboard=0.5*' \
    'r-SnowballC=0.5*' \
    'r-NLP=0.1*' \
    'r-DT=0.2' \
    'r-ggplot2=2.2*' \
    'r-RColorBrewer=1.1*' \
    'r-broom=0.4*' \
    'r-MASS=7.3*' \
    'r-randomforest=4.6*' && conda clean -tipsy

RUN conda config --add channels BIMSBbioinfo && \
    conda install --quiet --yes \
    'r-plotly=4.5.2' && conda clean -tipsy
