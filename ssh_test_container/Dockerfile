FROM ubuntu:latest

RUN apt update && apt install  openssh-server sudo -y
RUN apt install python3 sudo -y
RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1001 test 
RUN  echo 'test:password' | chpasswd
RUN service ssh start
EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]

WORKDIR /home
RUN chmod 777 /home
COPY test.py ./
RUN chmod 777 /home/ubuntu
