FROM docker.io/bitnami/minideb:bookworm

RUN install_packages wget ca-certificates vim less silversearcher-ag

#RUN wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh && bash Anaconda3-2022.05-Linux-x86_64.sh -b -p /opt/anaconda3

COPY  Anaconda3-2022.05-Linux-x86_64.sh /tmp/Anaconda3-2022.05-Linux-x86_64.sh 
RUN   bash /tmp/Anaconda3-2022.05-Linux-x86_64.sh -b -p /opt/anaconda3 && \
      rm /tmp/Anaconda3-2022.05-Linux-x86_64.sh

ENV PATH="/opt/anaconda3/bin:$PATH" \
    HOME="/app"

# Files for lesson 02
COPY 02_files/requirements.txt  /tmp/02_requirements.txt
RUN pip install -r /tmp/02_requirements.txt


#jupyterhub, mlflow
EXPOSE 8888 5000

WORKDIR /app
USER 1001

ENTRYPOINT [ "jupyter", "notebook", "--ip", "0.0.0.0" ]
