#Installing Docker on Ubuntu
```bash
# Update Software Repos
$ sudo apt-get update

# Remove old version if one exists
$ sudo apt-get remove docker docker-engine docker.io

# Install
$ sudo apt install docker.io

# Add to System Start
$ sudo systemctl start docker
$ sudo systemctl enable docker 
```