# Obuntu

A docker image based on `ubuntu:20.04` with some extra config for testing.

## Usage

- To use it locally

  ```bash
  docker run -it omarabdul3ziz/obuntu:grid bash
  ```

- To deploy on grid
  - Flist: `https://hub.grid.tf/omarabdul3ziz.3bot/omarabdul3ziz-obuntu-grid.flist`
  - Entry Point: `/init.sh`
  - Envs: `SSH_KEY`

## Dev notes

- The best way to manage starting

  ```bash
  #Dockerfile
  ENTRYPOINT [ "/init.sh" ] # main config
  CMD [ "sleep infinity" ] # to halt the container

  #init.sh
  exec $@ # execute the cmd after entrypoint
  ```

  in the case of deploying local you can override the `CMD` with the run command to be `bash`

- The limitation after converting to flist
  - no `ENV` or `ARG`: `export` them in entrypoint or while deployment
  - no `WORKDIR`: `cd` in the entrypoint
  - no `USER`: `su -` user in the entrypoint
  - no `CMD`: `exec ` in the entrypoint
  - no `ENTRYPOINT`: set in deployment
  - no `/etc/hosts`: `echo` in the entrypoint

## Image contains

- [x] vim
- [x] curl
- [x] ping
- [x] python3
- [x] ssh
- [x] node
- [x] yarn
- [ ] nginx
- [ ] docker
