# Ansible dnsmasq sudo nginx+php
> This repo installs dnsmasq app, creates users having sudo privileges, and a static web app built of nginx and php.

## Usage
Edit dnsmasq conf file, change a group and users names, and edit nginx.conf file before running the command that roll this all out.  
To install all mentioned above run:
```bash
terraform init
terraform apply --auto-approve
```
### Edit dnsmasq conf file
Go to roles > dnsmasq > templates > etc_dnsmasq.conf.j2 template file and change its content.

### Change a group and users names
Go to playbooks > superusers.yml.  
Find `superusers` group name and change it.  
Find user2, user3 users names and change them.  
You can change number of users.  

### Edit nginx.conf file
Go to roles > nginx-php > templates > nginx.conf.j2 template and change it.

### Edit document root
Go to roles > nginx-php > tasks > main.yml.  
Find `conveying files via template` task.   
Find `/opt/nginx/ansible/index.php` and change the path.  
Go to roles > nginx-php > templates > nginx.conf.j2 template.  
Find `root /opt/nginx/ansible;` and change the path.

### Edit index.php to other content
Use copy task or shell task to copy or clone your project to your document root directory.  

## Installation
You should have Terraform and Ansible on your host to roll that out.
You also should have Yandex.Cloud account and your credentials listed in main.auto.tfvars.sample.

## Acknowledgments
This repo was inspired by [skillfactory.ru](https://skillfactory.ru/devops#syllabus) team

## License
Follow all involved parties licenses terms and conditions.