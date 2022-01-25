To use this base image do the following: 
- Deploy with the base flist
- install your pkgs && write your scripts in /etc/zinit && zinit monitor <new_service>
- when everythig works fine, install requirments in dockerfile && copy the the services scripts to [ps dir](./ps)
- build, push, convert, deploy. worked?