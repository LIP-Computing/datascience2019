FROM python:3.6
LABEL maintainer="Samuel Bernardo <samuelbernardo.mail@gmail.com> & Giles Strong <giles.strong@outlook.com>"

WORKDIR /root/
# Install addittional features
RUN apt-get update && \
    apt-get --assume-yes install \
      wget \
      pkg-config \
      glue-sprite \
      python-six \
      libblas-dev \
      liblapack-dev \
      libssl-dev \
      gfortran \
      git \
      tar

#PIP
RUN pip --no-cache-dir install \
      glue \
      tensorflow==1.11.0 \
      keras==2.2.4 \
      jupyter \
      matplotlib==3.0.2 \
      numpy==1.15.2 \
      pandas==0.23.4 \
      seaborn==0.8.1 \
      scikit-learn==0.20.0

#rfpimp
RUN git clone https://github.com/parrt/random-forest-importances.git && \
    cd random-forest-importances/src && \
    pip install .

ENV KERAS_BACKEND tensorflow

EXPOSE 8888

CMD ["/run_jupyter.sh", "--allow-root", "--notebook-dir=/notebooks"]