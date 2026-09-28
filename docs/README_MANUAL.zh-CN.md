# 个人学术主页 · Academic Homepage

> **历史模板说明，不代表当前交付状态。** 当前已完成个人化，请优先阅读 [当前使用说明](../START_HERE.zh-CN.md)。下文的占位示例及部署指引保留作历史参考；涉及公开范围及现有功能时，以当前说明为准。

这是参照你提供的网站结构制作的独立静态主页：顶部导航、左侧个人资料、右侧学术内容，白底、灰色文字、蓝色链接。

**当前为占位版，不包含你的真实姓名、照片、履历、论文或联系方式，也尚未部署到公网。** 页面中的方括号内容和示例论文必须替换或删除后再发布。未填写的外部账号、论文资源以非链接标签显示，避免误跳转。

## 1. 先在本地打开

解压完整压缩包，双击 `index.html`，使用浏览器打开。

不需要安装 Jekyll、Node.js、Ruby 或其他开发依赖。样式、图标和脚本均在 HTML 文件内，无需下载外部字体或组件。主页在禁用 JavaScript 时仍可阅读；手机折叠菜单属于可选增强功能。

文件结构：

```text
academic_homepage/
├── index.html        主页：简介、研究、论文、经历
├── START_HERE.zh-CN.md 当前使用说明
├── CHECKS.md         本次交付的测试记录
├── .nojekyll          静态网站标记文件
├── robots.txt        搜索引擎抓取规则
├── sitemap.xml       首页站点地图
├── google95683f43e0f470c6.html  Google 所有权验证文件
└── assets/
    └── README.txt    照片和公开资源的放置说明
```

## 2. 修改内容

用纯文本编辑器打开 `index.html`，搜索 `EDIT`，按注释修改。不要用 Word 编辑 HTML。

| 搜索位置 | 修改内容 |
| --- | --- |
| `EDIT 01` | 网页标题、搜索摘要、分享摘要 |
| `EDIT 02` | 导航中的姓名 |
| `EDIT 03` | 头像 |
| `EDIT 04` | 侧栏姓名、身份、学校、地点和研究组 |
| `EDIT 05` | 邮箱、Google Scholar、GitHub、ORCID 链接 |
| `EDIT 06` | 资料完成后删除占位提示框 |
| `EDIT 07` | 个人简介 |
| `EDIT 08` | 研究方向 |
| `EDIT 09` | 论文、作者、年份、状态和真实资源链接 |
| `EDIT 10` | 教育与研究经历 |
| `EDIT 11` | 页脚姓名和更新时间 |

个人简介、研究、论文和教育经历统一在 `index.html` 中维护。

### 姓名和照片

将所有 `Your Name` 改成你的英文名，所有 `你的姓名` 改成你的中文名。默认头像中的 `YN` 是占位字母，不是真实人物照片。

把照片保存为 `assets/profile.jpg`，将 `EDIT 03` 后的整个头像 `div` 替换成：

```html
<img class="avatar" src="assets/profile.jpg"
     alt="Portrait of Your Name" width="166" height="166">
```

用你的实际姓名替换 `alt` 中的 `Your Name`。方形照片更便于裁切；页面会自动以圆形展示。头像图片的路径和文件名必须与上传文件一致。

### 联系方式

为了避免误导，占位版的 Email、Google Scholar、GitHub、ORCID 不是可点击链接。在 `EDIT 05` 下将相应的整条 `<li>...</li>` 换成自己的链接。例如：

```html
<li>
  <a class="social-link" href="mailto:your.name@example.com">
    <svg class="icon" aria-hidden="true"><use href="#i-mail"/></svg>
    Email
  </a>
</li>
<li>
  <a class="social-link"
     href="https://github.com/YOUR_USERNAME"
     target="_blank" rel="noopener noreferrer">
    <svg class="icon" aria-hidden="true"><use href="#i-github"/></svg>
    GitHub
  </a>
</li>
```

以上地址同样是格式示例；必须换成你的实际邮箱和账号。Google Scholar 与 ORCID 请填写你的完整个人资料链接。没有使用的平台可删除整条 `li`。替换链接时移除 `is-placeholder` 类名和 `add link` 字样。

### 论文和链接

两个 `article.publication` 是论文条目的格式示例，不代表任何真实成果。可以复制一个完整的 `article` 增加条目，也可以直接删除。

写入真实标题、作者顺序、年份、会议或期刊及发表状态；已发表、已接收、预印本和在投应明确区分。复制引用框中的 BibTeX 也必须替换为真实引用。

将占位资源 `span` 改为真正的链接：

```html
<a class="resource-link" href="assets/paper.pdf"
   target="_blank" rel="noopener noreferrer">PDF ↗</a>
```

把允许公开的论文文件放进 `assets/` 后再使用此链接。没有 PDF、代码或项目页面就删去相应资源标签；不要留空链接或填 `#`。外部链接需要完整的 `https://` 地址。

没有论文时，将该栏标题与导航中的 `Publications` 改成 `Research Projects`，使用真实研究项目介绍，并删除示例论文和 BibTeX。

### 中文内容

正文可直接替换为中文。若整站改为中文，把 `index.html` 开头的 `<html lang="en">` 改为 `<html lang="zh-CN">`，并相应翻译菜单和按钮。

## 3. GitHub Pages 发布

下面是与本模板匹配的方式，不需要套用 Jekyll 或 Academic Pages 的构建步骤。

1. 在 GitHub 创建一个公开仓库。做个人根主页时，仓库名应为 `你的GitHub用户名.github.io`。
2. 将**解压后的文件夹里面的内容**上传到仓库根目录，而不是只上传压缩包或在根目录再套一层 `academic_homepage` 文件夹。根目录应直接看到 `index.html`。保留 `.nojekyll`、搜索引擎配置和 Google 所有权验证文件；网页上传没有带上 `.nojekyll` 时，可以用 “Add file → Create new file” 创建一个名为 `.nojekyll` 的空文件。
3. 仓库 `Settings → Pages → Build and deployment`：`Source` 选择 `Deploy from a branch`，分支选择 `main`（以你的实际源码分支为准），目录选择 `/(root)`，保存。
4. 查看仓库 `Actions` 中的部署任务。成功后，用 `Settings → Pages` 显示的网站地址访问。

个人仓库的默认地址格式是：

```text
https://你的GitHub用户名.github.io/
```

也可以放在普通项目仓库，例如 `academic-homepage`。这时默认地址是：

```text
https://你的GitHub用户名.github.io/academic-homepage/
```

所有站内文件使用相对路径，可放在个人主页根目录或项目子路径中。**引用本地资源时不要随意加开头的 `/`**，否则项目站可能指向错误位置。

若同名仓库已存在并且已有内容，请先备份，不要覆盖现有网站。

GitHub 官方说明（核查于 2026-09-28）：

- Pages 网站类型与仓库命名：
  https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages
- 从分支发布的设置步骤：
  https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

本交付只提供文件，没有替你创建仓库、上传资料、购买域名或设置账号权限。

## 4. 发布前的检查

- 把姓名、机构、研究介绍和成果替换为真实内容；没有的栏目直接删除。
- 检查主页内所有方括号、`Your Name`、`YN`、`Template`、`[Year]` 等占位内容。不要误删代码中的 CSS 属性选择器或 JavaScript 语法。
- 删除 `template-notice` 占位说明。
- 复制引用提示中含有 `Replace template fields before use.`，正式发布时将该句删掉。
- 确认 `index.html` 使用 `<meta name="robots" content="index, follow">`，canonical 和站点地图仅指向首页的正式地址。这是收录许可，不保证搜索引擎一定收录；`noindex` 也不是访问权限控制。
- 逐个打开你的邮箱、学术账号和论文链接，确认指向正确内容。
- 在手机上查看页面，检查较长论文标题、姓名和机构名的换行。
- 不要上传密码、API 密钥、证件资料、私人住址、不可公开的研究材料或未获授权的论文版本。

## 5. 常见问题

**浏览器打开后只有代码。** 确认文件名是 `index.html` 而不是 `index.html.txt`，并选择使用浏览器打开。

**上线后出现 404。** 检查发布的分支和目录，根目录是否直接有 `index.html`，以及 Actions 中的部署是否成功。访问 GitHub 显示的 Pages 地址，而不是仓库代码页地址。

**头像或 PDF 显示不出来。** 检查文件是否真实上传，大小写、扩展名和路径是否完全一致。模板没有附带这些私人资料，不能只改链接而不上传文件。

**复制引用被浏览器拦截。** 页面会尝试本地文件兼容方式；仍被禁止时，会选中引用并提示手动使用 `Ctrl+C` / `⌘C`。

**不需要某个栏目。** 同时删除主内容中对应的 `section` 和顶部导航中的对应链接即可。可以保留至少一个主体 `section`，以维持当前滚动导航逻辑。

## 6. 设计来源

用户提供的参考网址：
https://tiancheng-htc.github.io/Tiancheng-Hu.github.io/

本版参考了学术主页的信息组织和简洁的左右栏结构。HTML、CSS 与交互为独立编写；没有打包参考站作者的头像、个人履历、论文内容、分析脚本或主题源码。本版不是 Academic Pages / Jekyll 主题包，不能直接使用该主题的 YAML 配置方式。
