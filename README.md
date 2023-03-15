#  Jupyter Notebook with Julia



### How to Run Locally ###

1. run lcBuid.sh to build the image 
1. run lcEnter.sh to enter the image
1. run make jupyter within the console to start the jupyter server

```bash
# Execute local container
. local_container.sh
```

```bash
# Install libraries to develop locally
make dev-compile
```
### Package Management ###

When developing using Docker, all the packages from the Manifest.toml will be installed during the build process.

To add/remove/update additional packages when developing, run a docker container and using the bash command line type
```bash
make julia
```
This will open a julia console using the project under "./project/". Press "]" to open the Pkg REPL and then proceed to add/remove/update packages.
```bash
add JuMP
```

### Setting up the container

Create a file **.env** and copy the contents of **.env.template** into it. This file should contain any custom information you want to pass to the container in form of environment variables, this file is not tracked by Git so that no conflicts are created by different users having different versions of this file.<br>

Open a GitBash terminal and run:

```bash
. local_container.sh
```

This should build the docker image, and also create and run a container exposing a bash terminal from the container to you.

### App

Following the standard configuration the app is served at port 8000 of the container which is forwarded to the port 8031 of the computer.

```bash
make local-deploy
```

Now go to [http://127.0.0.1:8031/](http://127.0.0.1:8031/) and see the documentation
