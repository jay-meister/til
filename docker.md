### docker
guide: https://medium.com/@yutafujii_59175/a-complete-one-by-one-guide-to-install-docker-on-your-mac-os-using-homebrew-e818eb4cfc3


#### Installation
```bash
brew install docker docker-machine
brew cask install virtualbox
# need password
# possibly need to address System Preference setting
docker-machine create --driver virtualbox default
docker-machine env default
eval "$(docker-machine env default)"
docker run hello-world
docker-machine stop default
```

```bash
# export variables
eval $(docker-machine env default)
docker run hello-world
```