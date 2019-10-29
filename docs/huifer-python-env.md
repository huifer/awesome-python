# python 环境
- Author: [HuiFer](https://github.com/huifer)
- Description: 本文介绍 python 环境


## python 版本选择
> 眼看着2020年即将来临 python2.x 即将不在被维护. 既然这样 python 版本当然选择3.x系列.

## python 基础环境
- 官网 : https://www.python.org/
- 安装
```shell script
wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tgz
tar -zxvf Python-3.7.0.tgz
mkdir /usr/local/python3
cd /usr/local/python3
./configure --prefix=/usr/local/python3
make && make install
ln -s /usr/local/python3/bin/python3.7 /usr/bin/python3
ln -s /usr/local/python3/bin/pip3.7 /usr/bin/pip3
```


## requirements
- requirements是描述 python 依赖的文本文件
- 描述规 `包名==版本号`
- 批量安装依赖包`pip install -r requirements.txt`
- 导出依赖`pip freeze >requirements.txt`


## 依赖安装
- pip 安装
    - https://packaging.python.org/guides/tool-recommendations/
- `pip install package_name`
- whl 安装
    - whl 文件下载地址 http://www.lfd.uci.edu/~gohlke/pythonlibs/
    - pip install whl_path
- setup.py 安装
    1. 下载源码
    1. python setup.py install 安装

## python env
- python 虚拟环境是指从 python 解释器上复制一个 python 解释器达到每个虚拟环境的 packages 互不影响,同时不会影响到全局 python

### 使用
- 安装
```pip install virtualenv```
- 创建
```virtualenv --no-site-packages venv``` 创建一个叫做 venv 的虚拟环境
- 激活
进入script目录运行activate.bat
- 退出
`deactivate`
- 删除
    直接删除目录即可
