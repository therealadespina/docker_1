# docker_1


docker-machine create --driver virtualbox Char

docker-machine stop Char

cp -R ~/.docker "goinfre/"$USER""_docker/""

rm -rf ~/.docker

ln -s "goinfre/"$USER""_docker/"" .docker

docker-machine start Char
