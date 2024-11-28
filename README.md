Install docker and docker compose @todo LINK 

docker build -t solana-anchor .

If you see an error like:

ERROR: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied

the execute

sudo chmod 777 /var/run/docker.sock

docker run -it -v .:/workdir solana-anchor

anchor init counter
