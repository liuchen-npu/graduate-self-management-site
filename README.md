# Graduate Self-Management (Standalone)

这是一个可独立部署的单页面研究生自我管理系统。

## 使用方式

- 访问部署地址即可使用，无需登录或安装。
- 所有数据只保存在当前浏览器本地存储中，不会上传到服务器。

## 数据与隐私说明

- 记录仅保存在浏览器 `localStorage` 中。
- 清理浏览器缓存或更换设备后，本地数据可能会丢失。
- 建议定期导出备份，方便迁移设备或浏览器。

## 导出与导入

- 点击页面右上角「保存位置」打开面板。
- 点击「更改保存位置」导出数据文件（JSON）。
- 点击「读取数据」选择之前导出的 JSON 文件进行恢复。

## 部署到 GitHub Pages

1. 新建仓库（例如 `graduate-self-management-site`），将本目录内容推送到该仓库根目录。
2. 在 GitHub 仓库的 **Settings -> Pages** 中选择：
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)`
3. 等待 Pages 构建完成。
4. 确保仓库根目录有 `CNAME` 文件，内容为：`gsm.liuchen.vip`

## DNS 配置

在域名解析中添加一条 CNAME 记录：

- 记录类型: CNAME
- 主机记录: `gsm`
- 记录值: `liuchen-npu.github.io`

生效后访问 `https://gsm.liuchen.vip`。


## 自动备份与自动读取

- 在「保存位置」面板中设置“自动备份文件”，浏览器会请求文件写入权限。
- 开启后会在页面隐藏/关闭时自动写入，并且每天至少自动备份一次。
- 启动时可自动读取该文件，免去手动导入。
- 需要支持 File System Access API 的浏览器（Chromium 系列浏览器体验最佳）。

## 样式构建

页面使用预编译的 Tailwind CSS。若修改了 `index.html` 中的类名或 `tailwind.css`，请在本地执行：

```bash
npm install
npm run build:css
```
