FROM datmo/keras-tensorflow:cpu-py35-notebook
LABEL maintainer="Samuel Bernardo <samuelbernardo.mail@gmail.com>"

WORKDIR /root/
# Add python 3.6
RUN add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get --assume-yes install python3.6
# Hack: solve wrong tensorflow-gpu module installed from base image
RUN pip uninstall tensorflow-gpu && \
    pip install tensorflow
# Install addittional features
RUN apt-get update && \
    apt-get --assume-yes install \
      wget \
      pkg-config \
      python \
      python-dev \
      python-pip \
      python-numpy \
      python-scipy \
      python-matplotlib \
      python-h5py \
      python-astropy \
      glue-sprite \
      python-six \
      libblas-dev \
      liblapack-dev \
      libssl-dev \
      gfortran && \
    pip --no-cache-dir install glue && \
    pip --no-cache-dir install -U scikit-learn && \
    pip install --user gwpy

CMD ["/run_jupyter.sh", "--allow-root"]