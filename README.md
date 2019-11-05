## 1.Jupyter Notebook Configuration (Jupyter Notebook远程服务配置)

### 1.1 Generate Configuration File 生成配置文件
```
jupyter notebook --generate-config 
```
### 1.2 Set Password 设置密码
```
jupyter notebook password
```
### 1.3 Modify Configuration File 修改配置文件
```
vim ~/.jupyter/jupyter_notebook_config.py
```
modify the following 4 configurations, delete # at the beginning

修改以下四个配置,并把每个开头的 # 注释去掉
```
c.NotebookApp.ip = '*' # 开启所有的IP访问，即可使用远程访问
c.NotebookApp.open_browser = False # 关闭启动后的自动开启浏览器
c.NotebookApp.port = 8888  # 设置端口8888，也可用其他的，比如1080，8080等等
c.NotebookApp.allow_remote_access = True
```
### 1.4 Start Notebook 启动Notebook
```
jupyter notebook
```
### 1.5 Remote Access 远程访问
Access http://hostip:8888，hostip is the ip address of your server


## 2. Jupyter Notebook Conda Multiple Environment Management <br>(Jupyter Notebook Conda多版本环境管理)

 Execute following steps for each environment you want to add to jupyter notebook
### 2.1 Activate Environment 激活环境
```
source activate your_env_name
```
'your_env_name' is your conda environment name
### 2.2 Install ipykernel 安装ipykernel
```
conda install ipykernel
```
### 2.3 Write environment into notebook 将环境写入到notebook中
```
python -m ipykernel install --user --name your_env_name --display-name "environment name shown in notebook"
```

