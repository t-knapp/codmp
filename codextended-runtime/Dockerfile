FROM i386/debian:buster

# You have to mount the games files root folder to containers location.
WORKDIR /opt/codmp

# Add runtime dependencies of codextended lib
RUN apt-get update && \
    apt-get -y install libidn11 libssh2-1 libmariadb3 librtmp1 libldap-2.4-2 libgssapi-krb5-2 && \
    ln -s /usr/lib/i386-linux-gnu/librtmp.so.1 /usr/lib/i386-linux-gnu/librtmp.so.0 && \
    echo "deb http://security.debian.org/debian-security jessie/updates main" > /etc/apt/sources.list && \
    apt-get update && \
    apt-get -y install libssl1.0.0

EXPOSE 28960/tcp 28960/udp 20500/udp 20510/udp

# Set-up codextended lib related stuff
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:.
ENV LD_PRELOAD=./codextended.so

# Run public server. Make sure dedicated.cfg is located in main-folder.
# You can also overwrite the parameters with docker run.
ENTRYPOINT [ "./cod_lnxded", "+set dedicated 2", "+exec dedicated.cfg" ]