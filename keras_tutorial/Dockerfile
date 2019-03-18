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
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*

#PIP
RUN pip --no-cache-dir install \
      glue \
      tensorflow==1.11.0 \
      keras==2.2.4 \
      notebook==5.4.1 \
      jupyter \
      matplotlib==3.0.2 \
      numpy==1.15.2 \
      pandas==0.23.4 \
      seaborn==0.8.1 \
      scikit-learn==0.20.0 \
      tornado==5.1.1 && \
    python -m ipykernel.kernelspec

#rfpimp
RUN git clone https://github.com/parrt/random-forest-importances.git && \
    cd random-forest-importances/src && \
    pip install .


# Set up Jupyter Notebook config
ENV CONFIG /root/.jupyter/jupyter_notebook_config.py
ENV CONFIG_IPYTHON /root/.ipython/profile_default/ipython_config.py 
RUN jupyter notebook --generate-config --allow-root && \
    ipython profile create
RUN echo "c.NotebookApp.ip = '0.0.0.0'" >>${CONFIG} && \
    echo "c.NotebookApp.port = 8888" >>${CONFIG} && \
    echo "c.NotebookApp.open_browser = False" >>${CONFIG} && \
    echo "c.NotebookApp.iopub_data_rate_limit=10000000000" >>${CONFIG} && \
    echo "c.MultiKernelManager.default_kernel_name = 'python3'" >>${CONFIG} 
RUN echo "c.InteractiveShellApp.exec_lines = ['%matplotlib inline']" >>${CONFIG_IPYTHON}
ENV KERAS_BACKEND tensorflow
EXPOSE 8888

CMD ["jupyter","notebook", "--allow-root", "--notebook-dir=/notebooks"]
