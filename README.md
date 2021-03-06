# vagrant-eclipse-packer
Packer build that downloads and installs Java, Maven, Gradle and Eclipse into any Ubuntu Vagrant box that already has Unity

This project is a build configuration that uses [Packer](https://www.packer.io) to build a Virtualbox image and pack it into a [Vagrant](https://www.vagrantup.com/) box.

At the end of the build, the generated box is published to Atlas so it can be used to create development environments with Vagrant. 

If all you want is a Vagrant box with Eclipse, you don't need to build a new one, just grab [the box generated by this build](https://atlas.hashicorp.com/danielgazineu/boxes/trusty64-eclipse).

## Pre-requisites
Vagrant, Packer and Virtualbox must be installed and available in the path.

## Usage

To build and deploy a new box, just run
```
./build.sh $ORIGINAL_USERNAME $ORIGINAL_BOX_NAME $ORIGINAL_VERSION $YOUR_ATLAS_USERNAME $DEST_ATLAS_BOX_NAME $DEST_ATLAS_BOX_VERSION
```
For example, I used the following command to generate this box https://atlas.hashicorp.com/danielgazineu/boxes/trusty64-eclipse/versions/0.0.2
```
./build.sh danielgazineu ubuntu-trusty64-unity 0.0.1 danielgazineu trusty64-eclipse 0.0.2
```
## Known Issues
This build is based on a set of shell scripts that will download and unpack Java, Maven, Gradle and Eclipse into specific locations in the generated box. 
It would be better to use a more robust provisioning system, like Chef, but I didn't have time to experiment with it yet. Pull requests are welcome! :)

## Contributing
1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D
