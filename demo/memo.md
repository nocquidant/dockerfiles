## Les commandes

. Stop all containers `docker stop $(docker ps -a -q)`
. Delete all containers `docker rm $(docker ps -a -q)`
. Delete all images `docker rmi $(docker images -q)`
. Delete all images wo tags `docker rmi $(docker images | grep '<none>' | tr -s ' ' | cut -d ' ' -f 3)`

