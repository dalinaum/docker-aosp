FROM dalinaum/aosp-sync
MAINTAINER Leonardo YongUk Kim <dalinaum@gmail.com>

RUN apt-get install -y vim
RUN echo "source build/envsetup.sh" >> /home/aosp/.bashrc

VOLUME ["/out"]

CMD /bin/bash
