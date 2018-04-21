
##### 1. 配置 ../hosts 文件
hosts
```
# eg.
[test]
172.17.0.2 id=1
172.17.0.3 id-2
172.17.0.4 id=3
```
##### 2. 配置 ../ run.yml
run.yml
```
# eg.
- hosts: test
  remote_user: root
  roles:
    - zookeeper
```
##### 3. 执行  

```
# 配置好ssh免密登录则不需要加 -k 参数
ansible-playbook -i hosts run.yml -k
```

##### [详细介绍](http://waterandair.top/install-zookeeper.html)