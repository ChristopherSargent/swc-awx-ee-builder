## swc-awx-ee-builder
* [awx-ee](https://github.com/ansible/awx-ee)
* [install ansible-builder](https://ansible-builder.readthedocs.io/en/stable/installation/).

### Install ansible-builder
* Installed on WSL Ubuntu24.04
1. pip3 install ansible-builder

### Build awx-218-ee 
* Add ansible core 2.18.5, community.docker, ansible.utils, community.general and community.crypto

1. cp execution-environment.yml execution-environment.yml.ORIG
2. vim execution-environment.yml
* Update as needed
3. ansible-builder build -v3 -t quay.io/ansible/awx-218-ee
4. podman images
```
REPOSITORY                         TAG         IMAGE ID      CREATED        SIZE
quay.io/ansible/awx-218-ee         latest      0d8b5ec366db  15 hours ago   2.25 GB
```
5. podman image save -o /mnt/c/Users/cas/Desktop/awx-ee-builder/awx-218-ee.tar quay.io/ansible/awx-218-ee:latest
6. Upload image to https://drive.google.com/file/d/1p9BYUCZ7Ieqo90K64VblLu377iGLqf9B/view?usp=drive_link

