# JupyterLab on Jetson

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![](<https://img.shields.io/static/v1?label=Systems&message=linux/amd64,linux/arm64&color=orange>)
![](https://img.shields.io/static/v1?label=Software&message=JupyterLab&color=red)


*** Copy Right 2020 Kevin Yu. All rights reserved.

*** Author: Kevin Yu

*** Update Time: 2021/01/07

*** Contact: kevinyu211@yahoo.com | www.hikariai.net

This repo aims to give you clear instructions on how to install **Jupyter Software** (Jupyter Lab, Jupyter Notebook) on Jetson devices. It should work on any x86 PCs or Mac as well.

The guide below is a demonstration of the deployment, and the usage **JupyterLab** on Jetson. However, The usage features of Jupyter Notebook are very close to those of JupyterLab, so you should be able to apply the same techniques in Jupyter Notebook as well.

![](https://github.com/yqlbu/jetson_lab/blob/master/demo_screenshots/thumbnail.png)

## Docs

- [Wiki (EN)](https://github.com/yqlbu/jetson_lab/blob/master/Wiki.md)

## Quick Install

#### Install with Script

```bash
curl -fsSL https://raw.githubusercontent.com/yqlbu/jetson_lab/master/install.sh | bash -
```

#### Install with Docker

```bash
$ docker run --name jupyterlab -d \
  -e TZ=Asia/Shanghai \
  -p 8888:8888 \
  -v /appdata/jupyterlab:/opt/app/data \
  hikariai/jupyterlab:latest
```

#### Run the app

```bash
$ jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data \
  --allow-root --NotebookApp.token='' --NotebookApp.password='' \
  --LabApp.terminado_settings='{"shell_command": ["/bin/bash"]}'
```