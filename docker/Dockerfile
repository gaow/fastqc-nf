FROM continuumio/miniconda
MAINTAINER Gao Wang <gaow@uchicago.edu>

RUN apt-get -y install ttf-dejavu

COPY conda.yml .
RUN \
   conda env update -n root -f conda.yml \
&& conda clean -a
