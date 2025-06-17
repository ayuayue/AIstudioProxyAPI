# Docker 部署文件

这个目录包含了 AI Studio Proxy API 项目的所有 Docker 相关文件。

## 📁 文件说明

- **`Dockerfile`** - Docker 镜像构建文件
- **`docker-compose.yml`** - Docker Compose 配置文件
- **`.env.docker`** - Docker 环境配置模板
- **`README-Docker.md`** - 详细的 Docker 部署指南

## 🚀 快速开始

### 1. 准备配置文件

```bash
# 进入 docker 目录
cp .env.docker .env
nano .env  # 编辑配置文件
```

### 2. 启动服务

```bash
# 进入 docker 目录
cd docker

# 构建并启动服务
docker compose up -d

# 查看日志
docker compose logs -f
```

### 3. 版本更新

```bash
# 在 docker 目录下
bash update.sh
```

## 📖 详细文档

完整的 Docker 部署指南请参见：[README-Docker.md](README-Docker.md)

## 🔧 常用命令

```bash
# 查看服务状态
docker compose ps

# 查看日志
docker compose logs -f

# 停止服务
docker compose down

# 重启服务
docker compose restart

# 进入容器
docker compose exec ai-studio-proxy /bin/bash
```

## 🌟 主要优势

- ✅ **统一配置**: 使用 `.env` 文件管理所有配置
- ✅ **版本更新无忧**: `bash update.sh` 即可完成更新
- ✅ **环境隔离**: 容器化部署，避免环境冲突
- ✅ **配置持久化**: 认证文件和日志持久化存储

## ⚠️ 注意事项

1. **认证文件**: 首次运行需要在主机上获取认证文件
2. **端口配置**: 确保主机端口未被占用
3. **配置文件**: `.env` 文件需要放在 `docker/` 目录下，确保正确获取环境变量
4. **目录结构**: Docker 文件已移至 `docker/` 目录，保持项目根目录整洁
