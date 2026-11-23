# 小红书社区生态研究报告 · GitHub Pages 部署包

此目录可直接作为一个 GitHub 仓库的根目录，通过 GitHub Pages 发布为公开网页。部署完成后，把 Pages 页面给出的链接发给他人，即可直接在浏览器查看报告，无需下载 HTML 或登录 GitHub。

## 当前报告版本

`index.html` 对应《小红书社区生态研究报告_李云璐_讲稿适配版.html》，按 8 段讲稿逐页更新内容与内嵌讲稿，统一“5 名用户小范围调研”口径，并修正朋友踢球受伤的案例、产品建议与指标。

最新布局已移除右上角“讲稿”按钮，并将研究设计页的左右两栏调整为等宽。内嵌讲稿仍可按 `N` 键打开。所有资源均在 HTML 内，不需要后端、数据库、API Key、npm 或构建步骤。

| 文件 | 用途 |
| --- | --- |
| `index.html` | 网站首页，最新讲稿适配版报告 |
| `.nojekyll` | GitHub Pages 静态文件标记，跳过 Jekyll 处理 |
| `README.md` | 本部署说明，不会替换报告首页 |

压缩包没有额外的父级目录。解压后，将上述文件直接放在 GitHub 仓库根目录。

## 通过 GitHub 网页部署

### 1. 新建仓库

1. 登录 GitHub，打开 https://github.com/new 。
2. 仓库名称建议填写 `xhs-community-report`，也可使用其他英文名称。
3. 可见性选择 **Public**。公开仓库可以使用 GitHub Free 的 Pages 功能。
4. 勾选 **Add README**，点击 **Create repository**。

### 2. 上传解压后的文件

1. 在电脑上解压本 ZIP。
2. 打开仓库的 **Code** 页面，点击 **Add file → Upload files**。
3. 上传 `index.html`、`.nojekyll`、`README.md`。本包的 README 可直接覆盖新建仓库时自动生成的 README。
4. 点击 **Commit changes**，提交到 `main` 分支。
5. 确认进入仓库首页就能看到 `index.html`：它应在根目录，不能再套一层文件夹。

**上传的是解压后的文件，而不是 ZIP 本身。**

如果文件管理器隐藏了 `.nojekyll`，可打开“显示隐藏文件”，或在仓库中点击 **Add file → Create new file**，将文件名设为 `.nojekyll` 后提交。该文件仅用于标记，内容可留空；如果界面要求输入内容，写一行 `Static site` 也可以。

### 3. 开启 GitHub Pages

1. 点击仓库的 **Settings**。
2. 点击左侧 **Pages**。
3. 在 **Build and deployment** 区域设置：

| 设置项 | 选择 |
| --- | --- |
| Source | `Deploy from a branch` |
| Branch | `main`（如默认分支另有名称，选择实际分支） |
| Folder | `/(root)` |

4. 点击 **Save**。
5. 等待部署完成。可在 **Actions** 页查看发布任务状态，再回到 **Settings → Pages** 点击 **Visit site**。

无需手动添加 GitHub Actions workflow；本包采用从分支直接发布的方式。GitHub 会在后台运行 Pages 发布任务。

### 4. 获取并分享网址

以仓库名 `xhs-community-report` 为例，默认网址形式是：

```text
https://<你的GitHub用户名>.github.io/xhs-community-report/
```

这是网址格式示例，并非已经创建的访问链接。请以 **Settings → Pages → Visit site** 给出的真实网址为准。

分享 Pages 的网址（域名通常是 `github.io`），即可直接打开交互报告。仓库文件页的 `github.com/.../blob/...` 地址展示的是代码，不能替代报告访问网址。

GitHub 官方说明：提交后，页面更新发布可能需要最多约 10 分钟。部署完成后可用浏览器无痕窗口打开真实网址，确认访客无需登录即可访问。

## 本地预览与更新

- 本地预览：双击 `index.html`，用现代浏览器打开。页面无需网络下载额外资源。
- 更新报告：保持文件名 `index.html`，在仓库根目录上传替换并提交；Pages 会按配置重新发布，分享网址保持不变。
- 保留翻页、目录、全屏、打印、场景切换和主题弹窗；内嵌讲稿可按 `N` 键打开，右上角“讲稿”按钮已移除。

## 常见问题

### 打开显示 404

确认 Pages 发布任务已完成、Source 选中了 `Deploy from a branch`、分支选择正确、文件夹选择 `/(root)`，且仓库根目录中存在小写的 `index.html`。刚发布时可稍后刷新。

### 打开看到说明文档或源码

请从 **Settings → Pages → Visit site** 打开站点，同时确认 `index.html` 位于所选发布目录根部。不要使用仓库里的文件预览页或 Raw 地址作为报告分享链接。

### 无法选择 main 分支

先完成文件上传并提交，使仓库中存在至少一个提交；若你的分支实际叫其他名称，请选择对应分支。

### 本地找不到 .nojekyll

点开文件可能默认隐藏。按上文的方法显示隐藏文件，或在 GitHub 仓库根目录新建该文件即可。

## 内容一致性校验

最新讲稿适配版 HTML 与 `index.html` 均为 102,461 字节，SHA-256 相同：

```text
505a8abb94c558f6e8c87b0f48de4d8f0e186eb96bf2be46125bafacee23482f
```

## GitHub 官方参考

- [创建 GitHub Pages 站点](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [配置发布来源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Pages 简介及默认网址格式](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)
