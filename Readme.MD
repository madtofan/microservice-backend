# Pre-requisite
- Install Rust by running `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
- Install Cargo-make library by running `cargo install --force cargo-make`
- Get and install Docker from `https://docs.docker.com/get-docker/`

# Install ProtoC
- Get the latest version of protoc and place it to a variable `PROTOC_VERSION=$(curl -s "https://api.github.com/repos/protocolbuffers/protobuf/releases/latest" | grep -Po '"tag_name": "v\K[0-9.]+')`
- Navigate to your downloads folder eg: `cd ~/downloads/`
- Download the latest version of protoc `curl -Lo protoc.zip "https://github.com/protocolbuffers/protobuf/releases/latest/download/protoc-${PROTOC_VERSION}-linux-x86_64.zip"`
- Unzip the downloaded package `sudo unzip -q protoc.zip bin/protoc -d /usr`
- Set execute permission `sudo chmod a+x /usr/bin/protoc`
- Check if the installation is successful `protoc --version`
- Delete the downloaded zip file `rm -rf protoc.zip`

# Migration
- Install sqlx-cli `cargo install sqlx-cli` 
- Run migration `sqlx migrate run`

# Commands
- `cargo make clone`: Clones all the services repositories
- `cargo make build`: Build all Docker container from all repositories
- `cargo make start`: Build and start the containers
