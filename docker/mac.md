## Notes from installing [Docker](https://www.docker.com) on Mac

1. Install [Homebrew](http://brew.sh/).
  ```bash
  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

2. Install [VMWare](https://www.virtualbox.org/wiki/Downloads) v4.3.4+
  ```bash
  wget http://dlc-cdn.sun.com/virtualbox/4.3.20/VirtualBox-4.3.20-96996-OSX.dmg
  ```
Run installer.

3. Install [Vagrant](https://www.vagrantup.com/) v1.4.0+
  ```bash
  wget https://dl.bintray.com/mitchellh/vagrant/vagrant_1.7.1.dmg
	```
Run installer.

4. Install [Docker](https://www.docker.com/) __v.1.2.0__
```bash
brew tap homebrew/boneyard
cd $( brew --prefix )
brew versions docker
git checkout 9ccfc7e Library/Formula/docker.rb
brew unlink  docker
brew install docker
brew switch  docker 1.2.0
docker --version
```ref - https://gist.github.com/evgeny-goldin/636b408832524542c789

5. Install [dvm](http://fnichol.github.io/dvm/)
```bash
brew tap fnichol/dvm
brew install dvm
```

## Run

```bash
# Bring up your Vagrant/Docker VM
dvm up

# Set a DOCKER_HOST environment variable that points to your VM
eval $(dvm env)

# Run nginx server
docker run -d -P --name web nginx 
```

