FROM rtems5-arm-tools:5.1
LABEL Description="RTEMS 5.1 ARM Raspberry Pi build"
ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux

#
# Download and build a specific release of RTEMS,
# then build RTEMS for the ARM/Raspberry Pi
#    This can be customized for different targets and BSPs
#   
RUN  cd /usr/src && \ 
     #
     # download RTEMS
     #
     wget https://ftp.rtems.org/pub/rtems/releases/5/5.1/sources/rtems-5.1.tar.xz && \
     tar Jxf rtems-5.1.tar.xz && \
     #
     # Build RTEMS
     #
     cd rtems-5.1 && \
     ./bootstrap && \
     cd .. && \
     mkdir b-arm && \
     cd b-arm && \
       ../rtems-5.1/configure --target=arm-rtems5 \
       --enable-rtemsbsp="raspberrypi raspberrypi2" \
       --prefix=/opt/rtems/5.1 \
       --enable-networking \
       --enable-posix  && \
     make -j8 && \
     make install && \
     #
     # Clean up
     #
     cd .. && \
     rm -rf b-arm
