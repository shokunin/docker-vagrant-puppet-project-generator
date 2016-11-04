docker-vagrant-puppet-project-generator
---------------------------------------

This will generate a project with docker container setup with puppet.

There will also be a vagrant file for debugging in real-time.

example setup:

```
./gen_project --project testing  --docker-host hub.docker.com \
              --docker-org foo --docker-source-image ubuntu:16.04 \
              --ruby-version ruby-2.3.1 --terraform-version 0.7.7 \
              --ruby-gemset docker-packer  --vagrant-box ubuntu/xenial64 \
              --vagrant-source-url https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box
```

The project Readme.md file that will explain how to build and use the container
