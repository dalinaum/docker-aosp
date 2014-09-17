docker-aosp
===========

AOSP (Android Open Source Project) environment using Docker

Getting Started
---------------

To create an image, exceute the following command:
````
docker build -t dalinaum/aosp .
````

Run:
````
docker run -i -t dalinaum/aosp
repo sync
````
