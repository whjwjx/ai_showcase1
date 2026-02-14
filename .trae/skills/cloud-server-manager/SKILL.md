---
name: "cloud-server-manager"
description: "管理和操作远程云服务器。当用户需要连接、查看状态、部署项目或管理云服务器容器时，调用此 Skill 以获取连接参数和操作规范。"
---

# 云服务器管理 (Cloud Server Manager)

此 Skill 用于规范和简化对特定云服务器（deployer@115.191.10.0:45623）的管理操作。

## 连接信息 (Connection Info)

- **主机**: `115.191.10.0`
- **端口**: `45623`
- **用户**: `deployer`
- **认证方式**: SSH 密钥 (免密登录已配置)
- **本地私钥路径**: `$env:USERPROFILE\.ssh\id_ed25519`

## 常用命令模板 (Common Commands)

### 1. 基础连接与执行
使用 `BatchMode=yes` 确保自动化脚本不会因为交互提示而挂起：
```bash
ssh -p 45623 -o BatchMode=yes deployer@115.191.10.0 "<command>"
```

### 2. Docker 管理
- **查看所有容器**: `docker ps -a`
- **查看容器日志**: `docker logs <container_name>`
- **查看内存统计**: `docker stats --no-stream`

### 3. 项目路径
- **主项目目录**: `~/projects/StepOne/`
- **Nginx 配置**: `~/nginx-conf/`
- **备份目录**: `~/backups/`

## 操作规范 (Guidelines)

1. **安全性**: 永远不要在命令中明文传输密码。
2. **非交互式**: 始终使用 `-o BatchMode=yes` 进行自动化操作。
3. **状态确认**: 在进行部署或重启操作前，先运行 `docker ps` 确认当前状态。
4. **日志记录**: 执行关键操作后，检查 `~/logs/` 下的相关日志以确认执行结果。

## 触发场景 (Invocation Scenarios)

当用户提出以下需求时，应参考此 Skill：
- "查看服务器状态"
- "重启 StepOne 项目"
- "看看后端报错没"
- "服务器内存还够吗"
- "部署新代码到服务器"
