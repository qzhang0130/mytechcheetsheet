# Common commands
docker images # show all images
docker images --help  # show help information about command images
docker rmi <image id> # remove docker image
docker rmi $(docker images -q)  # remove all images
docker images -f dangling=true  # filter dangling images
docker run -dit <image name> # start an new container in detached mode
docker run -p 80:80 nginx  # run with porting, left on host, right on containter
docker stop <container id>   # stop the running container
docker start <container id>  # start a stopped container
docker log xxx   # show the status of the running container
docker ps  # show running containers
docker ps -a  # show all container
docker rm <container id>  # remove a container
docker rm -fv <container id>  # remove container, forcing, remove with volume
docker help <command>   # see help information
docker exec -it <container id> --user==root --password=xxxx  # go into container
docker volume ls   # list volume
docker volume rm <volume id>  # delete volume
docker volume rm $(docker volume ls -q)  # remove all volumes
docker stop $(docker ps -q)   # stop all containers
docker rm $(docker ps -aq)   # remove all containers
docker container prune     # remove stopped containers
docker inspect <container id>  # lot information, can see which volume asociated
docker volume ls -f dangling=true   # filter dangling volume
docker volume rm $(docker volume ls -qf dangling=true)   # delete dangling volume
docker inspect db  # extract ip address
