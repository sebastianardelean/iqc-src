ARG ROOT_CONTAINER=jupyter/base-notebook:latest


FROM $ROOT_CONTAINER

WORKDIR /app

USER root

RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    fonts-dejavu \
    unixodbc \
    unixodbc-dev &&\
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER ${NB_UID}

COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt
 