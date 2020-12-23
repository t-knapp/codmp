FROM i386/debian:buster

# You have to mount the git repo folder to containers location.
WORKDIR /opt/src

# Add tools and dependencies for building codextended
RUN apt-get update && \
    apt-get install -y build-essential nasm libz-dev libssl-dev libmariadbclient-dev libmariadb-dev-compat

ENTRYPOINT [ "/bin/bash" ]