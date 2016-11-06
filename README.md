# BI-SP2 Dockerfiles
Dockerfiles used on software team project @FIT_CTU (BI-SP2).

This repository contains the most of Dockerfiles we have used on our semester-project @FIT_CTU.

## Apigen
Used for generating PHP documentation.

### Usage
```shell
docker run --rm -v"$PWD/app:/app/src" -v"$PWD/docs:/app/docs" josefdolezal/fit-bi-sp2-apigen
```
The first attached volume points to your app source code, the second one is for apigen output. By default, we use the Bootstrap theme.
