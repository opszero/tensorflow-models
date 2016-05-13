all: build

deps:
	cd /tmp
	sudo apt-get install swig
	sudo apt-get install openjdk-8-jdk
	sudo apt-get install pkg-config zip g++ zlib1g-dev unzip
	wget https://github.com/bazelbuild/bazel/releases/download/0.2.2/bazel-0.2.2-installer-linux-x86_64.sh
	chmod +x bazel-0.2.2-installer-linux-x86_64.sh
	./bazel-0.2.2-installer-linux-x86_64.sh --user
	sudo -H pip install -U protobuf==3.0.0b2
	sudo -H pip install asciitree

build:
	cd tensorflow && ./configure
	bazel test syntaxnet/... util/utf8/...
