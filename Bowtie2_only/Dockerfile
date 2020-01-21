FROM ubuntu:16.04

MAINTAINER Yuichi Shiraishi <friend1ws@gmail.com>

RUN apt-get update && apt-get install -y \
    wget \
    bzip2 \
    make \
    gcc \
    unzip \
    zlib1g-dev \
    g++ \
    libsys-hostname-long-perl

ENV bowtie2_dir="/bowtie2-2.3.4.3"

# bowtie2
RUN wget https://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.3.4.3/bowtie2-2.3.4.3-linux-x86_64.zip && \
    unzip bowtie2-2.3.4.3-linux-x86_64.zip

ENV PATH="${bowtie2_dir}:${PATH}"

# samtools
RUN wget https://github.com/samtools/samtools/releases/download/1.3.1/samtools-1.3.1.tar.bz2 && \
    tar jxvf samtools-1.3.1.tar.bz2 && \
    cd samtools-1.3.1/htslib-1.3.1 && \
    ./configure §§ make && make install && \
    cd ../ && ./configure --without-curses && make && make install

