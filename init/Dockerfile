FROM ubuntu:12.04
MAINTAINER Leonardo YongUk Kim <dalinaum@gmail.com>

RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list
RUN echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections

RUN apt-get update
RUN apt-get install -y openjdk-7-jdk
RUN apt-get install -y git gnupg flex bison gperf build-essential
RUN apt-get install -y zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev
RUN apt-get install -y libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386
RUN apt-get install -y libgl1-mesa-dev g++-multilib mingw32 tofrodos
RUN apt-get install -y python-markdown libxml2-utils xsltproc zlib1g-dev:i386
RUN apt-get install -y oracle-java6-installer
RUN ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so

RUN echo "y" | adduser --disabled-password --quiet aosp
RUN mkdir /home/aosp/kitkat
RUN mkdir /home/aosp/bin
RUN curl https://storage.googleapis.com/git-repo-downloads/repo > /home/aosp/bin/repo
RUN chmod a+x /home/aosp/bin/repo
RUN echo "export PATH=~/bin:\$PATH" >> /home/aosp/.bashrc

RUN cd /home/aosp/kitkat; /home/aosp/bin/repo init -u https://android.googlesource.com/platform/manifest -b android-4.4.2_r2.0.1

ENV HOME /home/aosp
WORKDIR /home/aosp/kitkat

CMD ["/bin/bash"]
