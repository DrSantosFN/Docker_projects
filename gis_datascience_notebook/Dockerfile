# Jupyter/datascience-notebook on Docker Hub: https://hub.docker.com/r/jupyter/datascience-notebook
# Jupyter/datascience-notebook on Github: https://github.com/jupyter/docker-stacks
# Source (datascience-notebook): https://www.youtube.com/watch?v=UXxUcZDSNwA
# Source (minimal-notebook): https://github.com/vladiuz1/py3-jupyter-docker-compose
# Size datascience-notebook: 5.66GB (including GDAL and others)
# Size minimal-notebook : 2.77GB

FROM jupyter/datascience-notebook
#FROM jupyter/minimal-notebook   

LABEL maintainer="santos.fernandeznoguerol@tudublin.ie"

# Copy the requirements.txt file
COPY requirements.txt requirements.txt

# Install Python packages
RUN conda install -c conda-forge gdal
RUN conda install -c conda-forge psycopg2
RUN python3 -m pip install -r requirements.txt

# Example on how to install R packages
#RUN conda install --quite --yes \
#    'r-postgresql' \
#    'r-getpass' \
#    'r-lme4' \
#    conad clean --all -f -y && \
#    fix-permisions "$(CONDA_DIR)" && \
#    fix-permisions "/home/$(NB_USER)"
