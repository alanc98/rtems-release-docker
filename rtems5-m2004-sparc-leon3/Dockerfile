FROM rtems5-m2004-sparc-tools:latest
LABEL Description="RTEMS 5 m2004 release SPARC LEON3 build"
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
     wget https://ftp.rtems.org/pub/rtems/releases/5/5.0.0/5.0.0-m2004/sources/rtems-5.0.0-m2004.tar.xz && \
     tar Jxf rtems-5.0.0-m2004.tar.xz && \
     #
     # Build RTEMS
     #
     cd rtems-5.0.0-m2004 && \
     ./bootstrap && \
     cd .. && \
     mkdir b-sparc && \
     cd b-sparc && \
       ../rtems-5.0.0-m2004/configure --target=sparc-rtems5 \
       --enable-rtemsbsp=leon3 \
       --prefix=/opt/rtems/5.0.0-m2004 \
       --enable-networking \
       --enable-posix  && \
     make -j8 && \
     make install && \
     #
     # Clean up
     #
     cd .. && \
     rm -rf b-sparc
