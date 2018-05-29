## Ansible test

## Inventory/Hosts conifg

使用 `vagrant ssh-config` 命令生成 ssh-config 输出到 ~/.ssh/config 文件中：

```
$ vagrant ssh-config >> ~/.ssh/config
$ ssh master
```

## Vagrant安装 `vagrant-hostmanager` 插件维护虚拟机 hosts 文件

```
$ vagrant plugin install vagrant-hostmanager
$ vagrant hostmanager
[master] Updating /etc/hosts file...
[node1] Updating /etc/hosts file...
[node2] Updating /etc/hosts file...
```
