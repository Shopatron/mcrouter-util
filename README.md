# mcrouter-util

To build rpm:

* launch centos 7 AMI
* yum update -y
* yum install -y git vim screen
* cd /root/
* git clone https://github.com/shopatron/mcrouter-util.git
* cd mcrouter-util
* git submodule init
* git submodule update
* cd fpm
* ./build-rpm.sh
* .rpm is created at /root/

When folly or mcrouter src need to be updated

* cd fpm/src/submodule_directory
* git checkout v1.0
* cd ..
* git add submodule_directory
* git commit -m "moved submodule to v1.0"
* go into build-rpm.sh and update version number of fpm
* git push


Todo:

* compile folly and ragel and store binary
* I will probably need to precompile automake (latest version of mcrouter requires newer version than yum repo provides)
* udpate documentation to only use release branch of mcrouter and folly
* in the mcrouter repo there is a FOLLY-COMMIT file that assoicates what version of folly to use for a given release of mcrouter