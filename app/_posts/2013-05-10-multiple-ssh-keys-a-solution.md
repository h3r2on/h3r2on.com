---
date: 2013-05-10
layout: post
slug: multiple-ssh-keys-a-solution
title: Multiple SSH keys a solution
comments: true
categories:
- tooling
tags:
- ssh
- git
- github
- bitbucket
---

Dealing with multiple SSH keys can be a nightmare especially across multiple machines. In my development I use 2 different GIT hosts, github.com, Bitbucket. Setting this up on my Mac was always a giant pain as there was always one key that would not get auto loaded by my `.ssh/config` file constantly requiring me to `$ ssh-add` the required key.

The issue was I had multiple keys in the root .ssh directory and it was only loading the root `id_rsa` key on boot. Which meant I had to manually add the other keys when I needed them.

The solution was much simpler than I thought and provides better management of my keys. The answer, folder per domain or key so now my `~/.ssh` dir looks like this:

    .ssh/
      bitbucket/
        id_rsa
        id_rsa.pub
      github/
        id_rsa
        id_rsa.pub

and my `.ssh/config` file looks like:

    Host github.com
      User git
      Hostname github.com
      PreferredAuthentications publickey
      IdentityFile ~/.ssh/github/id_rsa
    Host bitbucket.org
      User git
      Hostname bitbucket.org
      PreferredAuthentications publickey
      IdentityFile ~/.ssh/bitbucket/id_rsa

Now except for unlocking my ssh keys for use, you do have a password on your ssh keys right?, all my git ssh keys are loaded on boot and simple to use and manage. Adding a new key?
  
    $ mkdir ~/.ssh/DOMAIN
    $ ssh-keygen -t rsa -C "Your_Email@example.com"

You'll be greeted by this message

    # Creates a new ssh key, using the provided email as a label
    # Generating public/private rsa key pair.
    # Enter file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter] 

So to add it to our new folder enter (on a mac)
    
    /user/you/.ssh/DOMAIN/id_rsa

It will then ask you for a password and repeat that password and your key is generated. Then just add your new key to the config file and you'll be all set. 