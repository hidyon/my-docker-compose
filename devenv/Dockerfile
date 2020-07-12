FROM ubuntu:18.04

RUN apt update
RUN apt install -y curl
RUN apt install -y vim
RUN apt install -y nodejs npm
RUN npm install n -g
RUN n stable
RUN apt purge -y nodejs npm
RUN apt install -y git
RUN apt install -y less
RUN apt install -y python3
RUN apt install -y python3-pip
RUN pip3 install -U pip
RUN apt install -y locales
RUN locale-gen ja_JP.UTF-8
RUN npm install -g express-generator
RUN npm install -g @vue/cli
RUN npm install -g yarn
RUN apt install -y sudo

ENV USER usr01
ENV HOME /home/${USER}
ENV SHELL /bin/bash
RUN useradd -m ${USER}
RUN gpasswd -a ${USER} sudo
RUN echo "${USER}:usr01pass" | chpasswd
RUN sed -i.bak 's/${HOME}:/${HOME}:${SHELL}/' /etc/passwd
USER ${USER}
WORKDIR ${HOME}
RUN echo "export LANG=ja_JP.UTF-8" >> ~/.bashrc

