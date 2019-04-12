# env-injection-demo

## Goals
Create a complete cycle (especially within CI) that can create/manage/use env/config/secret securely for teams leveriging VCS such as git.

## Why?
- to prove injecting ENVs to VMs without compromising security
- to document how to do all the stuff to achieve the goal

## How it works
Use docker-compose to simulate different hosts doing different things at different point of times

### Writer
> it simulates a process of encrypting secrets

Writer read unencrypted files or values and encrypt them via ansible-vault

### Reader
> it simulates a part of a process triggered possibly via CI which need to decrypt secret
Reader read encrypted files or values and decrypt them via ansible-vault

### Consumer
> it simulates another part of a process triggered possibly via CI which need to consume decrypted secret
Consumer read decrypted files or values and use it against target via ansible

### Target
> it simulates a target VM that need env injection and other process such as a process triggered by CI

It's a minimal os + tools sets that represent regular VM listening to ssh requests to be altered.


## Prerequisites
- Docker, docker-compose
- this code is being developed and tested on mac

## Evaluate
`$ docker-compose up`

## WIP
still significant missing parts exist and more will be added soon
