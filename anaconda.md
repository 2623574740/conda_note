anaconda是python的环境管理工具，可以理解成前端的nvm；python各个环境的管理。

# <font face="">Download</font>

初学使用anaconda，官方下载地址：[Anaconda | The World's Most Popular Data Science Platform](https://www.anaconda.com/)

1. 安装前请卸载本机上所有的python环境
2. 安装后，在cmd  中无法使用conda命令，请将安装目录下的如下路径加入系统变量中
	```tex
	E:\anaconda;
	E:\anaconda\Library\mingw-w64\bin;
	E:\anaconda\Library\usr\bin;
	E:\anaconda\Library\bin;
	E:\anaconda\Scripts;
	E:\anaconda\bin;
	E:\anaconda\condabin
	```

# Command

## 查看conda版本

```bash
conda --version
```
## 环境管理

### 换源

#### 查看当前源

```shell
conda config --show
```

#### windows
```shell
# cmd中依次执行如下命令
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

> 恢复默认源
>
> ```shell
> conda config --remove-key channels
> ```

#### Mac OS

略（还没有在本人的MacBook上装anaconda）

### 配置环境安装路径

Windows系统，默认将环境安装在C盘:floppy_disk:，所以改到其他地方更好！（如果C盘足够大，可以不改）

1. 在C盘用户目录【C:\Users\username】下找到.condarc文件

2. 打开.condarc文件，添加如下内容

   ```shell
   envs_dirs:
     - D://anaconda3//envs
   ```

3. 保存并关闭.condarc文件，执行<code>conda create -n 环境名 python=版本号</code>命令，看看是否生效
4. <font color="red">如果未生效，查看文件 D://anaconda3//envs 权限，将Users权限全部授权为允许（耗时较长）</font>

### 查看本地环境

```shell
conda env list
```

### 查看conda配置

```shell
conda info
```

### 创建

```shell
# 创建环境
conda create -n 环境名 python=版本号
```

### 卸载

```shell
# 卸载环境
conda remove -n 已存在环境名 --all
# 或者
conda env remove --name 已存在环境名
# 或者
conda remove --prefix=路径 --all
```

### 切换

```shell
conda activate 环境名
```

### 退出

```shell
# 退出当前环境
conda deactivate
```

## 包管理

### 安装

```shell
# conda会自动安装依赖项，所以安装目标包即可
conda install 包名=版本
# 或 舍去包名，默认安装最新版
conda install 包名
```

### 更新

```shell
conda update 包名
```

### 卸载
```shell
conda remove 包名
```

### 查看
```shell
conda list
```

### 搜索
```shell
conda search 包名
```

# pycharm配置conda环境

File → Setting  →  Project: python → Python Interpreter → Add Interpreter → Conda Environment 

将安装目录下的_conda.exe完整路径填入，点击 Load Environment即可
![image-配置步骤图](https://gitee.com/JarryShu/conda_note/raw/master/imgs/pycharm_config.jpg)
![](.\imgs\pycharm_config.jpg)
