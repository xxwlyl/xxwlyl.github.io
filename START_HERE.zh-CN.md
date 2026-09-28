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
- `assets/profile.jpg`：正脸毕业照原图；圆形取景通过首页 CSS 控制。
- `robots.txt`：允许搜索引擎抓取，并提供站点地图地址。
- `sitemap.xml`：列出首页的正式地址。
- `sitemap.txt`：同一首页地址的纯文本地图，供 Search Console 排查地图抓取问题时单独提交。
- `google95683f43e0f470c6.html`：用户提供的 Google Search Console 所有权验证文件；验证后继续保留文件名与内容。
- `CHECKS.md`：本次检查结果及测试边界。
- `.nojekyll`：静态站点标记，迁移网站时保留。

网站不依赖外部字体、分析服务或前端框架。正文与导航在禁用 JavaScript 时仍可使用。

About、Research、Publications 和 Education 都在同一页。启用 JavaScript 时，普通点击栏目、姓名或 Back to top 只滚动并更新当前定位地址，不新增浏览器历史记录；“返回”可回到上一个实际访问的页面。直接打开带 `#publications` 等标记的链接仍能定位栏目，Ctrl/Cmd 点击及中键打开链接保留浏览器默认行为。禁用 JavaScript 时使用原生锚点导航。

此前已经产生的栏目跳转历史不会被自动清除；可在新标签页重新打开主页体验更新后的返回行为。

## 后续修改

修改姓名、教育或论文时，更新 `index.html` 中对应内容。Blowfish、SIGIR 2026 的 EDQC 和 ComGAT-PPIS 均提供已核实的 Paper、Code 链接；Chameleon 暂不添加资源链接。Paper 指向出版社页面或公开预印本，Code 指向对应的作者代码仓库。BibTeX 展示和复制功能已移除。

个人简介、研究、论文和教育经历统一展示在首页。已按用户要求移除重复的独立 CV 页面及入口；原始 CV 仅作为资料来源，当前网站没有提供 PDF 附件。

已按用户要求开放搜索收录：首页使用 `index, follow`，`robots.txt` 允许抓取，`sitemap.xml` 仅列出首页。canonical 使用正式地址 `https://xxwlyl.github.io/`。这些设置允许抓取和收录，不保证立即出现在搜索结果中。

Google Search Console 使用“网址前缀”资源 `https://xxwlyl.github.io/` 和“HTML 文件上传”验证方式。验证文件地址为 `https://xxwlyl.github.io/google95683f43e0f470c6.html`，请长期保留。用户提供的 2026-09-28 截图已确认首页编入 Google 索引；是否在具体姓名查询中展示或排名靠前，仍由 Google 决定。

验证成功后，在“网址检查”中输入 `https://xxwlyl.github.io/` 并请求编入索引；在“站点地图”中提交 `https://xxwlyl.github.io/sitemap.xml`。当前未代为执行账号内的验证或索引提交。未来更换域名时，需同步修改首页 canonical、`og:url`、`robots.txt` 和 `sitemap.xml` 中的地址，并重新确认 Search Console 资源及验证方式。

用户反馈 XML 地图在 Search Console 中仍显示“无法抓取”，但 Google 实时网址测试已通过，网站端 HTTP 和 XML 检查也正常。已新增 `https://xxwlyl.github.io/sitemap.txt` 作为不同地址、不同格式的对照排查入口；它只包含首页的完整网址，符合 Google 支持的纯文本地图格式。在已显示网址前缀的地图提交框中填 `sitemap.txt` 并提交一次，再查看该新记录的结果。此措施不代表已确认旧报告的错误原因或保证抓取成功。

两份地图应保持相同的首页地址，迁移域名时也要同步修改 `sitemap.txt`。`robots.txt` 继续引用原 XML 地图，无需反复改动已通过检查的首页内容。

原始资料、解析记录及浏览器测试工具应一直放在网站目录外。迁移时仅复制本目录，不要把其上级目录作为网站根目录。

## GitHub Pages 发布

仓库的 `main` 分支根目录直接保存 `index.html`、`.nojekyll`、`assets/`、`robots.txt`、`sitemap.xml` 和 Google 验证文件。在仓库 `Settings → Pages` 中选择 `Deploy from a branch`、`main` 和 `/(root)`，点击 Save。

网站目标地址为 `https://xxwlyl.github.io/`。是否已上线应以实际部署记录及访问结果为准，提交源码成功本身不表示 Pages 已启用。

后续在本目录修改网页或照片后，检查差异，提交对应文件并执行 `git push`。Pages 启用后，推送发布分支会触发网站更新。
