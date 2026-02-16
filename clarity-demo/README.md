# Clarity Demo

本演示展示了 VMware Clarity Design System 的 UI 组件使用方法。

## 目录

- [Clarity Design System 简介](#clarity-design-system-简介)
- [Microsoft Clarity 用户行为分析](#microsoft-clarity-用户行为分析)
  - [获取 Project ID 步骤](#获取-project-id-步骤)
  - [查看用户行为数据](#查看用户行为数据)
- [GitHub Pages 部署指南](#github-pages-部署指南)
- [常见问题排查](#常见问题排查)

---

## Clarity Design System 简介

Clarity Design System 是 VMware 开源的企业级设计系统，提供：

- 高质量的 UI 组件
- 完整的设计指南
- 无障碍访问支持
- 响应式设计

官方文档：https://clarity.design

---

## Microsoft Clarity 用户行为分析

Microsoft Clarity 是微软提供的免费用户行为分析工具，可以收集：

| 功能 | 说明 |
|------|------|
| **热图** | 用户点击、滚动、停留的区域 |
| **会话录制** | 回放用户的操作过程 |
| **死点击** | 用户点击无效区域的情况 |
| **性能指标** | 页面加载时间等 |

### 获取 Project ID 步骤

#### 1. 注册/登录 Microsoft Clarity

访问 https://clarity.microsoft.com

- 使用 Microsoft 账号登录
- 或使用 GitHub 账号登录
- 或使用 Google 账号登录

#### 2. 创建新项目

登录后点击 **"Add new project"**，填写：

| 字段 | 填写内容 |
|------|----------|
| **Project Name** | 项目名称，如 `NJU Demo` |
| **Website URL** | 网站地址，如 `https://用户名.github.io/仓库名` |

#### 3. 选择安装方式

创建项目后，选择 **"Manual installation"**（手动安装）

#### 4. 获取 Project ID

在显示的代码中找到 Project ID：

```javascript
<script type="text/javascript">
    (function(c,l,a,r,i,t,y){
        c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
        t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
        y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
    })(window, document, "clarity", "script", "你的Project ID在这里");
</script>
```

Project ID 就是最后一引号中的字符串，如 `vib4tlb6xn`

#### 5. 在代码中集成

将以下代码添加到每个 HTML 文件的 `<head>` 标签中：

```html
<script type="text/javascript">
    (function(c,l,a,r,i,t,y){
        c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
        t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
        y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
    })(window, document, "clarity", "script", "你的Project ID");
</script>
```

#### 6. 查看已有项目的 Project ID

如果忘记了 Project ID：

1. 登录 https://clarity.microsoft.com
2. 点击项目名称
3. 左侧菜单选择 **Settings** → **Installation**
4. 即可看到 Project ID

### 查看用户行为数据

#### 1. 登录 Clarity 仪表板

访问：https://clarity.microsoft.com

使用创建项目时的账号登录

#### 2. 进入项目

登录后，点击项目名称（如 "NJU Demo"）

#### 3. 查看各类数据

| 功能 | 位置 | 说明 |
|------|------|------|
| **仪表板概览** | Dashboard | 访问量、用户数、会话数等概览 |
| **热图** | Heatmaps | 点击热图、滚动热图、注意力热图 |
| **会话录制** | Recordings | 回放用户的实际操作过程 |
| **洞察** | Insights | 死点击、快速点击、错误点击等分析 |

#### 4. 数据延迟说明

| 情况 | 延迟时间 |
|------|----------|
| 新安装代码 | 需要等待 **几小时** 才能看到数据 |
| 已有流量 | 数据通常 **几小时内** 更新 |

#### 5. 验证是否正常工作

1. 访问您的网站 `https://用户名.github.io/仓库名/`
2. 在页面上进行一些点击、滚动操作
3. 等待几小时后，登录 Clarity 查看是否有数据

#### 6. 没有数据的可能原因

如果 24 小时后仍然没有数据，可能是：

| 原因 | 解决方案 |
|------|----------|
| 网站访问量太少 | 分享网站链接，增加访问量 |
| 代码安装位置不正确 | 确保 Clarity 代码在 `<head>` 标签内 |
| 浏览器广告拦截插件 | 检查是否有广告拦截插件阻止追踪 |
| 网站无法正常访问 | 确认网站可以正常打开 |

---

## GitHub Pages 部署指南

### 1. 初始化 Git 仓库

```bash
git init
git add .
git commit -m "Initial commit"
```

### 2. 创建 GitHub 仓库

1. 访问 https://github.com/new
2. 填写仓库名称（如 `nju-demo`）
3. 选择 **Public**（公开）
4. 点击 **Create repository**

### 3. 推送代码到 GitHub

```bash
git remote add origin https://github.com/用户名/仓库名.git
git branch -M main
git push -u origin main
```

### 4. 启用 GitHub Pages

1. 进入仓库的 **Settings**
2. 左侧菜单选择 **Pages**
3. **Source** 选择 `Deploy from a branch`
4. **Branch** 选择 `main`，**Folder** 选择 `/(root)`
5. 点击 **Save**

### 5. 等待部署完成

- 部署通常需要 1-3 分钟
- 在 **Actions** 标签页可以查看部署状态
- 部署成功后会显示访问地址：`https://用户名.github.io/仓库名`

---

## 常见问题排查

### 问题 1：Microsoft Clarity 登录失败

**错误信息：**
```
"We had an issue processing your request. Please try clearing your cookies..."
Error code: 101
```

**解决方案：**

| 方法 | 操作步骤 |
|------|----------|
| 清除 Cookie | 浏览器设置 → 清除 `microsoft.com` 和 `clarity.microsoft.com` 的 Cookie |
| 使用无痕模式 | 按 `Ctrl + Shift + N` 打开无痕窗口访问 |
| 更换浏览器 | 尝试使用 Edge、Chrome、Firefox |
| 检查网络 | 关闭 VPN 或切换网络环境 |
| 联系支持 | 发送邮件至 clarityms@microsoft.com，附上 traceId |

---

### 问题 2：GitHub Pages 无法访问

**错误信息：**
```
ERR_CONNECTION_CLOSED
无法访问此网站
```

**诊断步骤：**

1. 检查 GitHub 服务状态：https://www.githubstatus.com
2. 使用在线工具检测：https://downforeveryoneorjustme.com

**可能原因及解决方案：**

| 原因 | 解决方案 |
|------|----------|
| DNS 传播延迟 | 等待 10-30 分钟后重试 |
| 本地 DNS 污染 | 修改 DNS 为 `223.5.5.5` 或 `119.29.29.29` |
| 代理软件冲突 | 调整代理规则或暂时关闭代理 |
| 地区网络限制 | 使用 Vercel 等替代部署平台 |

**修改 DNS 方法：**

```powershell
# 刷新 DNS 缓存
ipconfig /flushdns
```

或在网络设置中修改 DNS：
- 首选 DNS：`223.5.5.5`
- 备用 DNS：`119.29.29.29`

---

### 问题 3：代理软件导致无法访问

**诊断方法：**

运行命令检查 DNS 解析：
```bash
nslookup 用户名.github.io
```

如果返回 `198.18.x.x`，说明被代理软件劫持。

**解决方案：**

| 方法 | 操作 |
|------|------|
| 修改代理规则 | 在代理软件中将 `github.io` 添加到直连/代理列表 |
| 切换代理模式 | 从 PAC 模式切换到全局模式 |
| 暂时关闭代理 | 关闭代理软件后访问 |

---

### 问题 4：Chrome 清除浏览数据卡住

**解决方案：**

| 方法 | 操作步骤 |
|------|----------|
| 只清除特定网站 | 访问 `chrome://settings/content/all`，搜索并删除特定网站数据 |
| 使用无痕模式 | 按 `Ctrl + Shift + N`，无需清除数据 |
| 强制关闭 Chrome | 任务管理器结束所有 Chrome 进程后重试 |

---

### 问题 5：部署成功但看不到更新

**解决方案：**

```bash
# 确保本地更改已提交
git status

# 推送到 GitHub
git add .
git commit -m "Update content"
git push
```

GitHub Pages 会自动重新部署。

---

## 替代部署方案

如果 GitHub Pages 访问不稳定，可以使用以下平台：

| 平台 | 特点 | 地址 |
|------|------|------|
| **Vercel** | 国内访问稳定，自动部署 | https://vercel.com |
| **Netlify** | 功能丰富，免费 SSL | https://netlify.com |
| **Cloudflare Pages** | CDN 加速，免费 | https://pages.cloudflare.com |

### Vercel 部署步骤

1. 访问 https://vercel.com
2. 使用 GitHub 账号登录
3. 点击 **Add New...** → **Project**
4. 选择 `xuyafei0116/nju-demo` 仓库
5. Framework 选择 **Other**
6. 点击 **Deploy**

部署完成后获得 `https://nju-demo-xxx.vercel.app` 地址。

---

## 相关链接

- [Clarity Design System](https://clarity.design)
- [Microsoft Clarity](https://clarity.microsoft.com)
- [GitHub Pages 文档](https://docs.github.com/pages)
- [Vercel](https://vercel.com)
