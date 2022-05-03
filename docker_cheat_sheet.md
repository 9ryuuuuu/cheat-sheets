# docker cheat sheet

## Docker Commands

- Help
  ```Shell
  docker compose help
  ```
- Stop and remove containers and delete volumes.
  ```Shell
  docker compose down -v
  ```
- 
  ```Shell
  
  ```

- docker compose up
  - create and start container
- docker compose down
  - Stop and remove containers, networks
- docker compose down -v
  - コンテナにアタッチされたボリュームを削除する。
- docker compose build
  - サービスをビルド、リビルドする。
  
## よくあるエラー
- [Cannot find module for a node js app running in a docker compose environment](https://stackoverflow.com/questions/42040317/cannot-find-module-for-a-node-js-app-running-in-a-docker-compose-environment)
  - try
    ```Shell
    docker-compose down -v
    ```
  - After adding npm install to the Dockerfile, add node_modules to volumes
    ```Shell
    volumes:
      - ./backend/:/usr/src/app
      - /usr/src/app/node_modules
    ```

## start docker on wsl
- Start
    ```Shell
    sudo service docker start
    ```

- Test
  ```Shell
  $ docker run hello-world
  ```


## Install docker on linux
- [Reference](https://docs.docker.com/engine/install/ubuntu/)

- Uninstall old versions
    ```Shell
    sudo apt-get remove docker docker-engine docker.io containerd runc  
    ```

- Set up the repository
    ```Shell
    $ sudo apt-get update

    $ sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release

    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

    $ echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    ```
- Install Docker Engine
    ```Shell
    $ sudo apt-get update

    $ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

    ```

- Run docker
  ```Shell
  $ sudo service docker status

  $ sudo service docker start

  $ sudo service docker status

  $ sudo docker run hello-world
  ```

## Install docker-compose on linux
- [Reference](https://docs.docker.com/compose/install/)

- Download
  ```Shell
  $ DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
  
  $ mkdir -p $DOCKER_CONFIG/cli-plugins
  
  $ curl -SL https://github.com/docker/compose/releases/download/v2.4.1/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
  ```

- Apply executable permissions to the binary:
  ```Shell
  $ chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose
  ```

- Test
  ```Shell
  docker compose version
  ```

## Use docker command without sudo

- Add user to docker group
  ```Shell
  $ sudo gpasswd -a $USER docker

  # restart machine
  ```
