# Basic Docker Commands


### Downloading (Pulling) Docker Images From Docker Hub
To download a Docker image from Docker Repository run:

```
docker pull <image_name>:<image_version>
```

For instance, in order to download [image of Ubuntu](https://hub.docker.com/_/ubuntu) (version 23.04) run the following command:
```
docker pull ubuntu:23.04
```

After the command completes, you should be able to find the pulled image in the list printed by the command `docker image ls -a`.

In the subsequent subsections I am going to assume that you are working with pulled image of `ubuntu:23.04`.


### Creating a Container From Image

In order to create a container from available image, you need to use `docker container create` command. For instance, to create a container from the image of `ubuntu:23.04` run:

```
docker container create -i -t --name ubuntu:23.04 my_ubuntu
```

For exegesis of the flags used in the command above, cf. the excerpt from the help on `docker container create`:

```
 -i, --interactive                    Keep STDIN open even if not attached
     --name string                    Assign a name to the container
 -t, --tty                            Allocate a pseudo-TTY
```



### Starting and Stopping a Container

After you create a container using the `docker container create` (shorthand: `docker create`) the new container `my_ubuntu` will be in `Created` state.

In order to start the container run:

```
docker container start my_ubuntu
```

You can stop the container using:

```
docker container stop my_ubuntu
```


### Entering the `Ubuntu` Container
After your Ubuntu container is created and started, you can enter it using the command:

```
docker container exec -it my_ubuntu /bin/bash
```


Excerpt from the help of `docker container exec`:

```
  -i, --interactive          Keep STDIN open even if not attached
  -t, --tty                  Allocate a pseudo-TTY

```


### Alternative: `docker run` Command

The combination of the commands `docker container create` + `docker container start` can be replaced by a single command `docker run`. 

Hence, if you have image of `ubuntu:23.04` available, you can run:

```
docker container run -it 0120ea4307c5
```

to create, start and enter the `ubuntu` container.
 


Note: `0120ea4307c5` is the `IMAGE ID` of the pulled `ubuntu:23.04` image.

