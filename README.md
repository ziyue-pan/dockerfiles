# ziyue-dockerfile

This repository is for all kinds of dockerfiles I created for developing.

## 1. FlexBison

```bash
$ cd flexbison
$ docker build --no-cache -t flexbison-image .
$ docker run --rm -ti -v ${HOME}/Desktop/course/CP/Lab:/lab flexbison-image
```

## 2. SSEC

```bash
$ cd ssec
$ docker build --no-cache -t ssec-image .
$ docker run -it --cap-add=SYS_PTRACE --security-opt seccomp=unconfined -v ${HOME}/Desktop/course/SSEC/Labs:/SSEC ssec-image /bin/bash
```

## 3. NodeJS

```bash
$ cd nodejs
$ docker build --no-cache -t nodejs-image .
$ docker run -it -v ${HOME}/Desktop/course/SE/Lab/MediConnect-Front:/frontend -p 3000:3000 nodejs-image /bin/bash
```

## 4. oslab

```bash
$ docker build -t oslab .
$ docker run --name oslab -it -v ${HOME}/Desktop/github/os21fall-ta:/os21fall-ta oslab 
```
