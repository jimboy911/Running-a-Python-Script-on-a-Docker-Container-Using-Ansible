# Running-a-Python-Script-on-a-Docker-Container-Using-Ansible
Running a Python Script on a Docker Container Using Ansible

To Install:
```
sudo su
dnf install ansible
dnf install docker
```

Copy files into your server

Setup Docker Container:
```
docker build -t ssh_test_container:latest .
docker run -t ssh_test_container
```

To Run:
```
ansible-playbook test_remote.yml -i /home/admin/ansible_ssh_test/inventory/inventory.ini -vvv
```

What this will do is SSH into the docker container and then print out Hello World in the container.

The 172.17.0.2 is an IP address that's native to Docker (some kind of docker bridge network protocol). To check the IP address of your docker container:
```
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container-ID-or-name>
```
