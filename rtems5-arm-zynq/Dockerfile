FROM rtems5-arm-tools:5.1
LABEL Description="RTEMS 5.1 ARM Xilinx Zynq A9 QEMU + libbsd build"
ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux

#
# Download and build a specific release of RTEMS,
# then build RTEMS for the ARM/Xilinx Zynq A9 QEMU with LibBSD support
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
       --enable-rtemsbsp=xilinx_zynq_a9_qemu \
       --prefix=/opt/rtems/5.1 \
       --disable-networking \
       --enable-posix  && \
     make -j8 && \
     make install && \
     #
     # Clean up
     #
     cd .. && \
     rm -rf b-arm && \
     #
     # Get rtems-libbsd 
     #
     cd /usr/src && \
     wget https://ftp.rtems.org/pub/rtems/releases/5/5.1/sources/rtems-libbsd-5.1.tar.xz && \
     tar Jxf rtems-libbsd-5.1.tar.xz && \
     cd rtems-libbsd-5.1 && \
     ./waf configure --prefix="/opt/rtems/5.1" \
       --rtems-tools="/opt/rtems/5.1" \
       --rtems-bsps=arm/xilinx_zynq_a9_qemu \
       --buildset=buildset/default.ini && \
     ./waf && \
     ./waf install && \
     #
     # Clean up
     #
     cd .. && \
     rm -rf rtems-libbsd-5.1
