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
- `cv.html`：网页版 CV，包含研究兴趣、教育和论文。点击 Print / Save as PDF 可调用浏览器打印。
- `assets/profile.jpg`：正脸毕业照原图；圆形取景通过首页 CSS 控制。
- `robots.txt`：允许搜索引擎抓取，并提供站点地图地址。
- `sitemap.xml`：列出首页和网页版 CV 的正式地址。
- `CHECKS.md`：本次检查结果及测试边界。
- `.nojekyll`：静态站点标记，迁移网站时保留。
- `README.md`：CV 解析与后续维护约定；其中模板示例仅用于说明。

网站不依赖外部字体、分析服务或前端框架。正文与导航在禁用 JavaScript 时仍可使用。

## 后续修改

两份 HTML 独立保存正文，修改姓名、教育或论文时需要同时更新。Blowfish、SIGIR 2026 的 EDQC 和 ComGAT-PPIS 均提供已核实的 Paper、Code 链接；Chameleon 暂不添加资源链接。Paper 指向出版社页面或公开预印本，Code 指向对应的作者代码仓库。BibTeX 展示和复制功能已移除。

已有网页 CV 入口应继续保留。以后添加经确认可公开的 PDF 简历时，可另加一个 PDF 下载入口。当前网站没有提供 PDF 附件。

已按用户要求开放搜索收录：两个页面均使用 `index, follow`，`robots.txt` 允许抓取，`sitemap.xml` 列出首页和 CV。canonical 使用正式地址 `https://xxwlyl.github.io/` 和 `https://xxwlyl.github.io/cv.html`。这些设置允许抓取和收录，不保证立即出现在搜索结果中。

可在 Google Search Console 或 Bing Webmaster Tools 验证网站所有权后提交 `https://xxwlyl.github.io/sitemap.xml`；当前未代为提交或验证所有权。未来更换域名时，需同步修改两页 canonical、首页 `og:url`、`robots.txt` 和 `sitemap.xml` 中的地址。

原始资料、解析记录及浏览器测试工具应一直放在网站目录外。迁移时仅复制本目录，不要把其上级目录作为网站根目录。

## GitHub Pages 发布

仓库的 `main` 分支根目录直接保存 `index.html`、`cv.html`、`.nojekyll` 和 `assets/`。在仓库 `Settings → Pages` 中选择 `Deploy from a branch`、`main` 和 `/(root)`，点击 Save。

网站目标地址为 `https://xxwlyl.github.io/`。是否已上线应以实际部署记录及访问结果为准，提交源码成功本身不表示 Pages 已启用。

后续在本目录修改网页或照片后，检查差异，提交对应文件并执行 `git push`。Pages 启用后，推送发布分支会触发网站更新。
