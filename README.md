# gitlab-ansible
first you should add the below proxies to /etc/environment
```
root@gitlab:~# cat /etc/environment 
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"
HTTP_PROXY=http://YOUR_PROXY
HTTPS_PROXY=http://YOUR_PROXY
http_proxy=http://YOUR_PROXY
https_proxy=http://YOUR_PROXY
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

