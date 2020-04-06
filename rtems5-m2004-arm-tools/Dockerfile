FROM rtems5-m2004-base:latest
LABEL Description="RTEMS 5 m2004 release ARM tools build"
ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux

RUN  cd /usr/src && \ 
     #
     # Download and extract RTEMS Source Builder
     # 
     wget https://ftp.rtems.org/pub/rtems/releases/5/5.0.0/5.0.0-m2004/sources/rtems-source-builder-5.0.0-m2004.tar.xz && \
     tar Jxf rtems-source-builder-5.0.0-m2004.tar.xz && \
     #
     # build the ARM RTEMS toolchain
     #
     cd rtems-source-builder-5.0.0-m2004/rtems && \
     ../source-builder/sb-set-builder --prefix=/opt/rtems/5.0.0-m2004 5/rtems-arm && \
     #
     # Clean up
     #
     cd /usr/src && \
     rm -rf rtems-source-builder-5.0.0-m2004

ENV PATH="/opt/rtems/5.0.0-m2004/bin:${PATH}"
