FROM ubuntu:bionic

LABEL authors="Gabriele Baldoni"

RUN apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get -y install libev4 libssl1.1 python3-pip curl
RUN pip3 install flask zenoh==0.3.0 yaks==0.3.0.post1 flask-cors
RUN curl -Lo /tmp/zenoh.deb https://github.com/eclipse-fog05/fog05/releases/download/v0.1.0/libzenoh-0.3.0-ubuntu-amd64.deb
RUN dpkg -i  /tmp/zenoh.deb
COPY ./teleop_server.py /root/server.py

CMD python3 /root/server.py $ZENOH