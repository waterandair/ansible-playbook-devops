用 ansible 在快速管理常用开发环境

### 一 测试环境

**操作系统:** ubuntu:16.04  
**ansible:** 2.4.2.0  
**python:** 3.5.2

linux 集群用 docker 创建的三个 linux 容器模拟
**docker:** 18.02.0  
**容器**: waterandair/sshd  
**容器用户名/密码:** root/root

### 二 使用
#### 1. java(jdk)
##### (1) 配置 hosts 文件
hosts
```
# eg.
[test]
172.17.0.2
172.17.0.3
172.17.0.4
```
##### (2) 配置 run.yml
run.yml
```
# eg.
- hosts: test
  remote_user: root
  roles:
    - jdk
```
##### (3) 执行  

```
# 配置好ssh免密登录则不需要加 -k 参数
ansible-playbook -i hosts run.yml -k
```
##### [详细介绍](http://waterandair.top/2018/03/22/install-jdk)

