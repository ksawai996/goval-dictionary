# Development Environment
## About
Build a devcontainer environment without docker desktop

## Build Vagrant environment
```
cd vagrant
vagrant up
```

## Build proxy container
```
vagrant ssh
cd /vagrant/vagrant/docker/squid/
docker compose up -d
```

## MacBook settings
1. Install docker client
```
curl https://download.docker.com/mac/static/stable/x86_64/docker-27.0.3.tgz -o docker-27.0.3.tgz
tar xzvf docker-27.0.3.tgz
sudo xattr -rc docker
mkdir ~/bin
cp -rf docker/* ~/bin/
echo 'export PATH=$PATH:~/bin' >> ~/.zshrc
```

2. Configure ssh-config
```
vagrant ssh-config >> ~/.ssh/config
```

3. Create docker context
```
docker context create vagrant-ubuntu --docker "host=ssh://default"
docker context use vagrant-ubuntu
```

4. Check docker context
```
docker info
```

## Open project in VSCode Dev Containers
1. Open VSCode
2. Install "Remote Development" extension
3. Click on "Reopen in container" in the lower left corner

## References
https://code.visualstudio.com/docs/devcontainers/containers
https://qiita.com/moritalous/items/26b0d0bdfed051cf62cc