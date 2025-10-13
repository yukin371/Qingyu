# 运维文档导航

## 📋 概述

本目录包含青羽书城前端的运维相关文档，涵盖部署、监控、日志、维护等运维操作指南。

## 📁 文档列表

### 🚀 部署指南
- [部署指南](./部署指南.md) - 前端应用部署完整流程
- [Docker部署](./Docker部署.md) - 使用Docker容器化部署
- [Nginx配置](./Nginx配置.md) - Nginx服务器配置指南
- [环境配置](./环境配置.md) - 不同环境的配置说明

### 📊 监控运维
- [性能监控](./性能监控.md) - 前端性能监控方案
- [错误监控](./错误监控.md) - 错误追踪和监控
- [用户行为分析](./用户行为分析.md) - 用户行为数据收集

### 📝 日志管理
- [日志收集](./日志收集.md) - 前端日志收集方案
- [错误日志](./错误日志.md) - 错误日志分析和处理

### 🔧 维护指南
- [维护手册](./维护手册.md) - 日常维护操作手册
- [故障排除](./故障排除.md) - 常见故障排查和解决
- [版本发布](./版本发布.md) - 版本发布流程和规范

## 🚀 快速部署

### 构建生产版本

```bash
# 安装依赖
npm install

# 构建生产版本
npm run build

# 预览构建结果
npm run preview
```

### Docker部署

```bash
# 构建镜像
docker build -t qingyu-frontend .

# 运行容器
docker run -d -p 80:80 qingyu-frontend
```

### Nginx配置示例

```nginx
server {
    listen 80;
    server_name qingyu.com;
    root /usr/share/nginx/html;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location /api {
        proxy_pass http://backend:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

## 📊 监控指标

### 性能指标
- **FCP (First Contentful Paint)** - 首次内容绘制
- **LCP (Largest Contentful Paint)** - 最大内容绘制
- **FID (First Input Delay)** - 首次输入延迟
- **CLS (Cumulative Layout Shift)** - 累积布局偏移

### 业务指标
- **PV (Page View)** - 页面浏览量
- **UV (Unique Visitor)** - 独立访客数
- **转化率** - 用户行为转化率
- **错误率** - 前端错误发生率

## 🔗 相关文档

- [构建配置](../engineering/构建配置.md) - Vite构建配置
- [环境配置](../engineering/环境配置.md) - 环境变量配置
- [后端运维文档](../../../Qingyu_backend/doc/ops/) - 后端运维指南

---

**最后更新**：2025年10月13日

