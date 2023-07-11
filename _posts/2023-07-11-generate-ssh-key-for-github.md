---
title: Config tow GitHub account ssh key for on computer
author: panxz
date: 2019-08-08 11:33:00 +0800
categories: [GitHub]
tags: [git]
pin: true
---

If you have two GitHub account, and you want to use two account in one computer, you can follow the steps below:

1. generate private key and public key for your accounts

`ssh-keygen -t rsa`

named "personal" and "work"

2. config for you GitHub project

copy public keys to https://github.com/settings/profile

3. config `~/.ssh/config`

```bash
Host work
  HostName bitbucket.org
  IdentityFile ~/.ssh/id_rsa_work
  User git
    
Host personal
  HostName bitbucket.org
  IdentityFile ~/.ssh/id_rsa_personal
  User git
```

4. Change GitHub project remote url from `git@github.com:xxx/xxx.git` to `personal:xxx/xxx.git` （or replace personal to work)

---
ref:
[Stack Overflow](https://superuser.com/questions/232373/how-to-tell-git-which-private-key-to-use/1519694#1519694)
