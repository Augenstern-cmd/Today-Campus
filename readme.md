# 今日校园自动填报python脚本

##  禁止任何人使用此项目提供付费的代挂服务，禁止任何牟利行为，api接口均已设置次数限制

### 今日校园每日自动提交疫情上报python脚本，支持邮件推送提交结果消息，此脚本仅适合四川信息职业技术学院学子使用，其他学校的同学请看完本说明，几乎支持所有学校

#### 本项目仅供学习交流使用，如作他用所承受的任何直接、间接法律责任一概与作者无关

#### 如果此项目侵犯了您或者您公司的权益，请立即联系我删除

## 项目说明：

- `config.yml` 默认配置文件
- `index.py` 完成自动提交的py脚本
- `generate.py` 帮助生成默认项配置的py脚本
- `requirements.txt` py依赖库以及版本说明文件

使用方式:
1.修改config.yml，只需要更改账号、密码、学校、地址，发布表单的问题即可，如果你不会配置表单组默认选项配置，请先配置好`user`信息之后本地执行`python generate.py`，根据提示信息手动输入，然后将分割线下的内容复制到配置文件中对应位置；如果问题中有省市县三级联动的位置，按`xx省/xx市/xx县`这个格式输入文本即可
2.此项目依赖python3运行环境，如没有，自行安装
3.进入目录下，安装依赖，命令

`pip3 install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple`
4.一切修改完之后运行即可，python3 index.py
5.配合腾讯云函数、linux、windows服务器上的计划任务，将本脚本挂在服务器上即可

说明:
1.此项目**默认配置仅适合四川信息职业技术学院学子**，也欢迎其他学校的同学提交适合自己学校的配置，命令为config_xxxx.yml，xxx为学校简称
2.此项目默认提交全部正常的情况，如果有其他情况，请自行在今日校园app上提交
3.如果是其他学校的同学，修改index.py中21行，修改读取配置文件名字，默认是config.yml，其他学校的同学可修改默认配置文件，也可复制默认配置文件后命令为config_xxx.yml，xxx为学校缩写
4.更多学校支持，敬请自行测试，没意外的话，大概是通用


设计思路:
1. 模拟登陆
2. 获取表单
3. 填充表单
4. 提交表单
5. 推送消息

### 封禁白嫖说明：

#### 白嫖党太多且几乎定时为同一时刻，导致高并发，使得提供模拟登陆API的服务器响应很不稳定，已采取封禁措施，封禁策略：未授权的账号只能使用每天一次模拟登陆API接口。

#### 解封联系QQ：1029789402

#### 也欢迎有服务器的同学贡献出服务器，造福本校同学；如不会部署模拟登陆API服务，可以联系我

## 关于模拟登陆API的说明，api借用子墨大神的

请看[`wisedu-unified-login-api`项目](https://github.com/ZimoLoveShuang/wisedu-unified-login-api.git)

# 关于金智教务系统的说明

1. 学校接入金智系统的方式有两种：`CLOUD`和`NOTCLOUD`
2. `CLOUD`方式对应的教务系统登陆页通常以`/iap/login`结尾
3. `NOTCLOUD`方式对应的教务系统登陆页通常以`/authserver/login`结尾
4. 目前以上两种接入方式，我提供的[模拟登陆API](https://github.com/ZimoLoveShuang/wisedu-unified-login-api.git)都能支持
5. 以上两种接入方式，登陆原理均为CAS，接口略有一点不同，但大同小异

