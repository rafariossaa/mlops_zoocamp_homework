FROM docker.io/bitnami/minideb:bookworm

RUN install_packages wget ca-certificates vim less silversearcher-ag

# Uncomment the `COPY` and comment the `RUN` line if you have downloaded anaconda manually
# I did this to save bandwith when experimenting with the image creation
RUN wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh && bash Anaconda3-2022.05-Linux-x86_64.sh -b -p /opt/anaconda3
#COPY  Anaconda3-2022.05-Linux-x86_64.sh /tmp/Anaconda3-2022.05-Linux-x86_64.sh 

RUN   bash /tmp/Anaconda3-2022.05-Linux-x86_64.sh -b -p /opt/anaconda3 && \
      rm /tmp/Anaconda3-2022.05-Linux-x86_64.sh

ENV PATH="/opt/anaconda3/bin:$PATH" \
    HOME="/app"

EXPOSE 8888

WORKDIR /app
USER 1001

ENTRYPOINT [ "jupyter", "notebook", "--ip", "0.0.0.0" ]
