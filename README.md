# gitlab-ansible
first you should add the below proxies to /etc/environment
```
root@gitlab:~# cat /etc/environment 
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"
HTTP_PROXY=http://pxuser:dkdevops@54.37.56.140:7777
HTTPS_PROXY=http://pxuser:dkdevops@54.37.56.140:7777
http_proxy=http://pxuser:dkdevops@54.37.56.140:7777
https_proxy=http://pxuser:dkdevops@54.37.56.140:7777
```
then you better create a virtualenv and use it:
```
python -m venv  ./gitlab
source gitlab/bin/activate
```
then you should install the requirement.txt
```
pip install requirement.txt
```
then you should install the gitlab role
```
ansible-galaxy install geerlingguy.gitlab
```
then you should specify the variable like gitlab_domain and other if you want in vars/main.yml
then apply the playbook
```
ansible-playbook -i inventory/hosts.yml  --become --become-user=root gitlab.yml
```

