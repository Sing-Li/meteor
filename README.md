## Meteor lightweight container - 1.1.0.2 for deployment

This deployment container is:

* ultra-lightweight in image size
* flexible - works well with Docker linking
* designed to work in Kubernetes orchestrations

Container size is very important if you pay for deployments.  

Larger image size means:

* more time wasted waiting for every push and pull
* paying more for transfer, storage, and RAM

With this container, the final image size for typical applications is around 130MB.  Other containers may create image size of up to 800MB for the same application.

Inspired by meteord.





 


