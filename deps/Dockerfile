# Dockerfile for KiCAD - build dependencies
#

FROM phusion/baseimage

ENTRYPOINT ["/sbin/my_init"]
CMD ["/bin/bash"]

RUN apt-get update

# Install KiCAD dependencies
# Have to add CodeLite repository to have WX 3.0
RUN apt-key adv --fetch-keys http://repos.codelite.org/CodeLite.asc
RUN apt-get install -y build-essential bzr bzrtools checkinstall cmake doxygen zlib1g-dev libwebkitgtk-dev libglew-dev libcairo2-dev libbz2-dev libssl-dev swig libwxbase3.0-dev libwxgtk3.0-dev

# Create the build directory (but do not populate it)
RUN mkdir /build

# Cleanup
RUN apt-get clean && rm -fr /var/libs/apt/lists/* /tmp/* /var/tmp/*

