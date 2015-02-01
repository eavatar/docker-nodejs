FROM eavatartech/basebox

ADD overlayfs.tar /

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

ENV PATH /opt/node/bin:$PATH
