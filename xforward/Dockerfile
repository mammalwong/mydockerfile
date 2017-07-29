ARG BASE_DEBIAN_IMAGE=debian:stretch

FROM ${BASE_DEBIAN_IMAGE}

RUN apt-get update && \
    apt-get install -y openssh-server xauth sudo && \
    mkdir -p /var/run/sshd

RUN useradd -m user && \
    usermod -aG sudo user && \
    chsh -s /bin/bash user && \
    chsh -s /bin/bash user && \
    echo root:password | chpasswd && \
    echo user:password | chpasswd

RUN echo PermitRootLogin yes >> /etc/ssh/sshd_config && \
    echo AllowTcpForwarding yes >> /etc/ssh/sshd_config && \
    echo X11Forwarding yes >> /etc/ssh/sshd_config && \
    echo X11DisplayOffset 10 >> /etc/ssh/sshd_config && \
    echo X11UseLocalhost no >> /etc/ssh/sshd_config && \
    echo Ciphers 3des-cbc,blowfish-cbc,cast128-cbc,arcfour,arcfour128,arcfour256,aes128-cbc,aes192-cbc,aes256-cbc,rijndael-cbc@lysator.liu.se,aes128-ctr,aes192-ctr,aes256-ctr,aes128-gcm@openssh.com,aes256-gcm@openssh.com,chacha20-poly1305@openssh.com >> /etc/ssh/sshd_config

ENTRYPOINT ["/usr/sbin/sshd", "-D"]
