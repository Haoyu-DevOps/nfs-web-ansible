# Ansible 自动化部署 NFS 和 Web 服务器

## 项目简介

本项目使用 **Ansible** 自动化部署 **NFS 文件共享服务** 和 **Nginx Web 服务器**，旨在通过自动化减少手动配置错误，提高部署效率，并优化日志管理。

通过本项目，你可以轻松地在多台机器上快速部署 NFS 服务和 Web 服务器，并使其无缝协作。

## 技术栈

- **Ansible**：自动化配置管理工具。
- **NFS**：网络文件系统，用于文件共享。
- **Nginx**：高性能 Web 服务器。

## 项目结构

ansible-nfs-web/
├── ansible.cfg              # Ansible 配置文件
├── hosts                    # Ansible 主机清单，定义了 NFS 和 Web 服务器的 IP 地址
├── nfs_server.yml           # NFS 服务器部署 Playbook
├── roles/
│   ├── nfs_server/          # NFS 服务器的角色
│   │   ├── handlers/        # 处理程序
│   │   ├── tasks/           # 任务
│   │   ├── templates/       # 模板文件
│   │   └── vars/            # 变量
│   └── web_server/          # Web 服务器的角色
│       ├── handlers/        # 处理程序
│       ├── tasks/           # 任务
│       ├── templates/       # 模板文件
│       └── vars/            # 变量
└── web_server.yml           # Web 服务器部署 Playbook

## 环境要求

- **操作系统**：CentOS 7 或其他兼容的 Linux 发行版
- **软件**：Ansible 2.x 或以上版本

## 安装与使用

### 1. 克隆项目

首先，将项目克隆到本地：

```bash
git clone https://github.com/yourusername/ansible-nfs-web.git
cd ansible-nfs-web

2. 配置 hosts 文件

在 hosts 文件中，配置 NFS 和 Web 服务器的 IP 地址：

[web]
172.16.1.7

[nfs]
172.16.1.31

3. 执行 Playbook 部署服务

运行以下命令来部署 NFS 和 Web 服务：
	•	部署 NFS 服务器：

ansible-playbook nfs_server.yml


	•	部署 Web 服务器：

ansible-playbook web_server.yml



项目说明
	•	nfs_server.yml：自动化部署 NFS 服务器，包括安装 NFS 服务、配置共享目录、启动 NFS 服务等。
	•	web_server.yml：自动化部署 Web 服务器，安装 Nginx 并配置其使用 NFS 挂载的目录作为 Web 根目录。
