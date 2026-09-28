# 个性化主页检查记录

最新补充（2026-09-28）：新增 `sitemap.txt` 供 Search Console 对照排查持续的 XML 地图抓取错误。文件仅含 `https://xxwlyl.github.io/` 一行，与 XML 地图及首页 canonical 一致；页面、XML 地图、robots.txt 和 Google 验证文件均未改动。用户截图已确认首页收录及 XML 地图实时测试通过，但地图报告仍报错；新增文本地图不代表 Google 已接受或错误已经解决。

下方为删除重复 CV 页面时的验证记录，本次未重复执行浏览器布局检查。

---

检查日期：2026-09-28。本轮按用户要求删除重复的独立 CV 页面、顶部导航与侧栏入口，以及首页底部的背景介绍链接。网站内容统一保留在首页。

## 本次验证

- 删除独立页面及全部首页入口，清理对应样式、图标和注释；站点地图仅包含 `https://xxwlyl.github.io/`。
- 比较修改前后的首页正文，除用户指定删除的一句链接文字外，个人介绍、研究方向、四篇论文和教育经历一致；导航脚本未改动。
- 使用 Chromium / Playwright 在根路径 `/` 和项目子路径 `/academic-homepage/` 下检查，覆盖 320 / 390 / 768 / 1440 像素宽度及开启、禁用 JavaScript，共 16 种组合，全部通过。
- 各组合均无页面级横向溢出；四个栏目和四篇论文完整显示，顶部导航仅保留 About、Research、Publications、Education。
- 开启 JavaScript 时，手机菜单在选择栏目后收起并将焦点移到目标；连续栏目跳转不增加浏览器历史记录，Back 一次返回来源页，Forward 返回最后栏目。
- 禁用 JavaScript 时，原生栏目导航可用；没有控制台或页面脚本错误。
- 人工查看 320 像素和 1440 像素首页截图，确认删除入口后布局正常。
- 本地原独立页面地址返回 404；主页中没有指向该地址的链接。
- 首页 `index, follow`、canonical、Google 验证文件及既有论文资源链接保持不变；站点地图 XML 验证通过。
- `git diff --check` 通过；公开网站包仅从 Git 跟踪文件生成，不含原始私人资料或浏览器检查工具。

## 验证边界

- 使用桌面 Chromium 的响应式视口，未在真实手机、Safari 或 Firefox 上实测。
- 本轮没有重新核实论文外链、邮箱投递或搜索引擎实际收录状态。
- Google 验证文件的存在不代表账号内已完成所有权验证或请求编入索引。
- 部署状态可从 [GitHub 部署记录](https://github.com/xxwlyl/xxwlyl.github.io/actions) 查看。

## 当前文件 SHA-256

```text
index.html e9d1f376a20c5acf81501bf62fcce5405354b42229462d07706b121de38bfb84
sitemap.xml dcf4366c79d6aef88ebfce98c3ba131f69efe7ed1ab5a42abc8648e12d2d02b5
google95683f43e0f470c6.html be3c01d569d6bc63a70b2255d0cfa559fe43597b808994542ae7c879ce5382ce
assets/profile.jpg 03f02c17a983e5b88f3633e14bf33ffb36d6c3803aefcab3d293e1d8c1c74e32
```
