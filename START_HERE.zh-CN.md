# Yilong Luo 个人主页

这是已根据 CV 整理好的英文静态网站，沿用白底、蓝色链接和左右栏布局。网站无需安装依赖或构建。目标仓库为 [xxwlyl/xxwlyl.github.io](https://github.com/xxwlyl/xxwlyl.github.io)；推送源码与启用网站托管是两个步骤。

## 预览

直接用浏览器打开 `index.html`，或在本文件所在目录运行：

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

然后访问 `http://127.0.0.1:8000/`。若端口被占用，可以换为 8001 并相应修改访问地址。

## 文件

- `index.html`：个人简介、研究方向、论文及教育经历。
- `cv.html`：网页版 CV，另含技能与语言。点击 Print / Save as PDF 可调用浏览器打印。
- `assets/profile.jpg`：生活照原图；圆形取景通过首页 CSS 控制。
- `CHECKS.md`：本次检查结果及测试边界。
- `.nojekyll`：静态站点标记，迁移网站时保留。
- `README.md`：CV 解析与后续维护约定；其中模板示例仅用于说明。

网站不依赖外部字体、分析服务或前端框架。正文与导航在禁用 JavaScript 时仍可使用。

## 后续修改

两份 HTML 独立保存正文，修改姓名、教育或论文时需要同时更新。论文引用由已提供的作者、标题、会议与年份组成；没有添加未经核验的 DOI、页码或资源链接。BibTeX 的原生折叠框和复制按钮位于每篇论文下方。

已有网页 CV 入口应继续保留。以后添加经确认可公开的 PDF 简历时，可另加一个 PDF 下载入口。当前网站没有提供 PDF 附件。

目前两个页面均保留 `noindex, nofollow`；这是搜索收录设置，不是访问控制。确定正式公开地址及收录意愿后，再按实际部署情况更新。本文不表示网站已经发布。

原始资料、解析记录及浏览器测试工具应一直放在网站目录外。迁移时仅复制本目录，不要把其上级目录作为网站根目录。

## GitHub Pages 发布

仓库的 `main` 分支根目录直接保存 `index.html`、`cv.html`、`.nojekyll` 和 `assets/`。在仓库 `Settings → Pages` 中选择 `Deploy from a branch`、`main` 和 `/(root)`，点击 Save。

网站目标地址为 `https://xxwlyl.github.io/`。是否已上线应以实际部署记录及访问结果为准，提交源码成功本身不表示 Pages 已启用。

后续在本目录修改网页或照片后，检查差异，提交对应文件并执行 `git push`。Pages 启用后，推送发布分支会触发网站更新。
