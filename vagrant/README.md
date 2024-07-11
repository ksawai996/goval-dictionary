# Development Environment
## About
Build a devcontainer environment without docker desktop

## MacBook Settings
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

## References
https://qiita.com/moritalous/items/26b0d0bdfed051cf62cc