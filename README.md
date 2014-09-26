docker-aosp
===========

[AOSP (Android Open Source Project)](https://source.android.com/) environment using [docker](https://docker.com/)

Usage
-----
````
docker run -it dalinaum/aosp
````

There is one volume, `/out`. If you need to use it, you can run this image with `-v` option to mount it.

If you're using	[boot2docker](https://docker.com/), you should [increase the volume size](https://docs.docker.com/articles/b2d_volume_resize/) and RAM to 4GB.


How to build your own docker images
-----------------------------------

To create an init image, exceute the following command:
````
cd init
docker build -t aosp-init .
````

To sync AOSP, execute the following command:
````
docker run --name init -it aosp-init
repo sync
````

````
docker commit init aosp-sync
````

To create a full image:
````
cd aosp
docker build -t aosp .
`````

To run:
````
docker run -it aosp
````

