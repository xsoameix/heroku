# Preparation

    $ export TERM=xterm
    $ alias ls='ls --color'

# Install nmap

    $ mkdir deb
    $ cd deb
    $ mirror=mirrors.kernel.org/ubuntu/pool/main
    $ wget http://$mirror/n/nmap/nmap_6.40-0.2ubuntu1_amd64.deb
    $ wget http://$mirror/libp/libpcap/libpcap0.8_1.5.3-2_amd64.deb
    $ wget http://$mirror/l/lua5.2/liblua5.2-0_5.2.3-1_amd64.deb
    $ wget http://$mirror/libl/liblinear/liblinear1_1.8+dfsg-1ubuntu1_amd64.deb
    $ wget http://$mirror/b/blas/libblas3_1.2.20110419-10_amd64.deb
    $ ar xf nmap_6.40-0.2ubuntu1_amd64.deb && \
      tar xf data.tar.* && rm control.tar.gz data.tar.* debian-binary
    $ ar xf libpcap0.8_1.5.3-2_amd64.deb && \
      tar xf data.tar.* && rm control.tar.gz data.tar.* debian-binary
    $ ar xf liblua5.2-0_5.2.3-1_amd64.deb && \
      tar xf data.tar.* && rm control.tar.gz data.tar.* debian-binary
    $ ar xf liblinear1_1.8+dfsg-1ubuntu1_amd64.deb && \
      tar xf data.tar.* && rm control.tar.gz data.tar.* debian-binary
    $ ar xf libblas3_1.2.20110419-10_amd64.deb && \
      tar xf data.tar.* && rm control.tar.gz data.tar.* debian-binary
    $ export LD_LIBRARY_PATH=/app/deb/usr/lib/x86_64-linux-gnu:/app/deb/usr/lib:/app/deb/usr/lib/libblas
    $ usr/bin/nmap -Pn ilibrorum[dot]net84[dot]net
