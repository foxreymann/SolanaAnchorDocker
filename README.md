A user-friendly Solana Anchor Docker solution that eliminates setup hurdles and simplifies the development workflow.

# SETUP

[Install Docker](https://docs.docker.com/desktop/)

Clone this repository:

`git clone git@github.com:foxreymann/SolanaAnchorDocker.git`

Enter the directory:

`cd SolanaAnchorDocker`

Build the image (might take some time on the first run):

`docker build -t solana-anchor .`

# ANCHOR DEVELOPMENT WORKFLOW

Start the container:

`docker run --name solana-anchor -d -v .:/workdir solana-anchor tail -f /dev/null`

Create an Anchor project:

`docker exec solana-anchor anchor init PROJECT_NAME`

Test the project:

`docker exec -w /workdir/PROJECT_NAME solana-anchor anchor test`

Build the project:

`docker exec -w /workdir/PROJECT_NAME solana-anchor anchor build`

Before deployment you have to start Solana Test Validator. Do this in a new terminal window to see the logs:

`docker exec -it solana-anchor solana-test-validator`

Deploy the project:

`docker exec -w /workdir/PROJECT_NAME solana-anchor anchor deploy`

# TIPS

Top open a Bash terminal session inside the Docker container:

`docker exec -it solana-anchor bash`

# TROUBLESHOOTING

If you see an error like:

`
ERROR: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied
`

the execute

`sudo chmod 777 /var/run/docker.sock`
