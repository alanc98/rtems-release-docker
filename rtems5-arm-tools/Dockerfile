FROM rtems5-base:latest
LABEL Description="RTEMS 5.1 rc2 release ARM tools build"
ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux

RUN  cd /usr/src && \ 
     #
     # Download and extract RTEMS Source Builder
     # 
     wget https://ftp.rtems.org/pub/rtems/releases/5/rc/5.1.0-rc2/sources/rtems-source-builder-5.1.0-rc2.tar.xz && \
     tar Jxf rtems-source-builder-5.1.0-rc2.tar.xz && \
     #
     # build the ARM RTEMS toolchain
     #
     cd rtems-source-builder-5.1.0-rc2/rtems && \
     ../source-builder/sb-set-builder --prefix=/opt/rtems/5.1.0-rc2 5/rtems-arm && \
     #
     # Clean up
     #
     cd /usr/src && \
     rm -rf rtems-source-builder-5.1.0-rc2

ENV PATH="/opt/rtems/5.1.0-rc2/bin:${PATH}"
