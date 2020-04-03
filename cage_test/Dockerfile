FROM ubuntu:16.04

MAINTAINER Shuichiro Komatsu <shuichiro.for.precious@gmail.com>

RUN apt-get update && apt-get install -y \
    wget \
    bzip2 \
    make \
    gcc \
    zlib1g-dev

# STAR
RUN wget https://github.com/alexdobin/STAR/archive/2.5.3a.tar.gz && \
    tar xzvf 2.5.3a.tar.gz && \
    mv STAR-2.5.3a/bin/Linux_x86_64_static/STAR /usr/local/bin

# samtools
RUN wget https://github.com/samtools/samtools/releases/download/1.3.1/samtools-1.3.1.tar.bz2 && \
    tar jxvf samtools-1.3.1.tar.bz2 && \
    cd samtools-1.3.1/htslib-1.3.1 && \
    ./configure §§ make && make install && \
    cd ../ && ./configure --without-curses && make && make install

# bedtools(ver2.28.0)
RUN wget https://github.com/arq5x/bedtools2/releases/download/v2.28.0/bedtools-2.28.0.tar.gz && \
    tar -zxvf bedtools-2.28.0.tar.gz && \
    cd bedtools2 && \
    make

# Kent Utility tools
RUN wget https://github.com/ENCODE-DCC/kentUtils/blob/master/bin/linux.x86_64/bedGraphToBigWig -P /usr/local/bin && \
    wget https://github.com/ENCODE-DCC/kentUtils/blob/master/bin/linux.x86_64/bigWigAverageOverBed -P /usr/local/bin