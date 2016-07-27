# Poppler Utils build tool

This is an ansible project designed to build Poppler Utils binaries. 

The binaries generated can be included in AWS Lambda projects if the Ansible playbook is run on an AWS Linux x64 machine.

This was my first stab at Ansible so may contain many errors, ommissions or terrible styling.

To run the playbook 
* install ansible (on a VM if using windows)

* provision a machine (Amazon Linux x64 if building for Lambda)

* ssh onto the machine and install python with `sudo yum install python`

* add the following lines to your /etc/ansibles/hosts file (with the correct IP address)

```
[lambda-build]
    12.34.56.789 ansible_user=ec2-user
    
```

* copy `./vars/private-sample.yml` to `./var/private.yml` and fill in the S3 bucket name if uploading binaries to S3

* run `ansible-playbook play_build.yml`