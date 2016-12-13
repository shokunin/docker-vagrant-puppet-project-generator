# vagrant-puppet-project-generator


This will allow you to generate either a docker or an AMI project.


## Docker

This will generate a project with docker container setup with puppet.

There will also be a vagrant file for debugging in real-time.

example setup:

```
./gen_project_docker --project testing  --docker-host dtr.domain.int \
                     --docker-org foo --docker-source-image dtr.domain.int/ops-base-images/puppet-xenial-base:latest \
                     --ruby-version ruby-2.3.1 --terraform-version 0.7.7 \
                     --ruby-gemset docker-packer  --vagrant-box ubuntu/xenial64 \
                     --vagrant-source-url https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box
```



## AMI

This will generate a project to build an AMI with puppet.

There will also be a vagrant file for debugging in real-time.

prep:

```
echo "export SOURCE_AMI=\"AMI-12345"\" > set_env.sh
echo "export AWS_REGION=\"us-west-1"\" >> set_env.sh
echo "export AWS_ACCESS_KEY_ID=\"KEY_ID"\" >> set_env.sh
echo "export AWS_SECRET_ACCESS_KEY=\"SECRET"\" >> set_env.sh

. set_env.sh
```
By default set_env.sh is in the git ignore file so it will not be checked in


example setup:

```
./gen_project_ami --project testing  \
                     --ruby-version ruby-2.3.1 --terraform-version 0.7.7 \
                     --ruby-gemset ami-packer  --vagrant-box ubuntu/xenial64 \
                     --vagrant-source-url https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box
```

The project Readme.md file that will explain how to build and use the AMI
