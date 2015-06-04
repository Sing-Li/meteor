##SIZE matters when it comes to Meteor app deployment

This deployment container is:

* ultra-lightweight in image size
* flexible - works well with Docker linking
* designed to work in Kubernetes orchestrations

Container size is very important if you pay for deployments.

Larger image size means:

* more time wasted waiting for every push and pull
* paying more for transfer, storage, and RAM

With this container, the final image size for typical applications is around 130MB. Other containers may create image size of up to 800MB for the same application.

Inspired by meteord.

### How to build a deployable image for your app

Your app will be converted into a Docker image. Then you can deploy the image with any container hosting service(s). 

Add following `Dockerfile` into the root of your app:

~~~shell
FROM singli/meteor
MAINTAINER Your Name
ENV ROOT_URL  http://yourapp.com
~~~

In your app directory, add a `set_env.sh` file and set all the environment variables that you need  (or for Docker container linking).   `set_env.sh` will be parsed at runtime - just before startup of the meteor app.

Then you can build the docker image with:

~~~shell
docker build -t yourname/app .
~~~

Then you can run your meteor image with

~~~shell
docker run -d \
    -p 8099:80 \
    yourname/app 
~~~

Then you can access your app at port 8099 of the host system.




 


