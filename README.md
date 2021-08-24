# How to Send Email Using Ansible Playbook via Gmail app password
This is an ansible playbook to Send Email Using Ansible Playbook via Gmail app password

### _Usage_

This Ansible playbook will perform following operations;

- Login Gmail Host
- Send email to recepient

## _Steps to be done_

With Ansible installed, you are ready to Send Email Using Ansible Playbook via Gmail app password by following the below steps.
```sh
$ git clone https://github.com/sebinxavi/ansible-email.git
$ cd ansible-email
```
###  Open the file 'email.yml' and update the Email login details

The Sample format is provided below,
```sh
        host: smtp.gmail.com
        port: 587
        username: "username@gmail.com"
        password: "email password"
        to: John Sam <johnsam12@gmail.com>
        subject: Ansible-report
        body: 'System {{ ansible_hostname }} has been successfully provisioned.'
```

- host :  Hostname of Email Server
- port: SMTP port number
- username: Username of email 
- password: Gmail app password or your email normal password
- to: Recpient Email address

Run the ansible-playbook from your master server by below command,

```sh
$ ansible-playbook email.yml
```

## _About the Ansible Playbook_
~~~
---
- name: Sending email using Ansible
  hosts: localhost
  connection: local
  tasks:
    - name: mail 
      mail:
        host: smtp.gmail.com
        port: 587
        username: "username@gmail.com"
        password: "email password"
        to: John Sam <johnsam12@gmail.com>
        subject: Ansible-report
        body: 'System {{ ansible_hostname }} has been successfully provisioned.'
      delegate_to: localhost
~~~

## Author
Created by [@sebinxavi](https://www.linkedin.com/in/sebinxavi/) - feel free to contact me and advise as necessary!

<a href="mailto:sebin.xavi1@gmail.com"><img src="https://img.shields.io/badge/-sebin.xavi1@gmail.com-D14836?style=flat&logo=Gmail&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/sebinxavi"><img src="https://img.shields.io/badge/-Linkedin-blue"/></a>
