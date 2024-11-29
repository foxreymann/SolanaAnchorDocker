# SETUP

Install docker and docker compose @todo LINK 

docker build -t solana-anchor .

If you see an error like:

ERROR: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied

the execute

sudo chmod 777 /var/run/docker.sock

# HOW TO / DEV WORKFLOW

docker run --name solana-anchor -d -v .:/workdir solana-anchor tail -f /dev/null

docker exec solana-anchor anchor init mars

docker exec -w /workdir/mars solana-anchor anchor test 

# TIPS

docker exec -it solana-anchor bash

# HOW TO 11/28

docker run -v .:/workdir solana-anchor anchor init mars

cd mars

docker run -v .:/workdir solana-anchor anchor test

# OLD

docker run -it -v .:/workdir solana-anchor

anchor init counter

docker run --name solana-anchor -d -v .:/workdir solana-anchor tail -f /dev/null

docker exec -t solana-anchor anchor init mars2

export anchor="docker exec -t solana-anchor anchor"

$anchor init mars5
