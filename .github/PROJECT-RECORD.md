# mymsnn 项目档案（PROJECT-RECORD）

> 本文档是 `mymsnn/mymsnn.github.io` 的项目记录。  
> 最后核对：2026-11-26  
> 当前档案状态：初始版；部分部署、主题来源及运行状态仍待核实。  
> 记录原则：只记录已由用户明确说明或通过 GitHub 实际读取确认的信息；不把推测写成事实。

---

## 1. 项目与仓库信息

### 1.1 主仓库

| 项目 | 记录 |
|---|---|
| 仓库全名 | `mymsnn/mymsnn.github.io` |
| GitHub 地址 | https://github.com/mymsnn/mymsnn.github.io |
| 仓库所有者 | `mymsnn` |
| 可见性 | Public（已核实） |
| 默认分支 | `master`（已核实） |
| 当前存在的分支 | 本次分支查询返回 `master` |
| 是否归档 | 否（已核实） |
| 仓库大小 | 最近一次查询约 10,933 KB；可能随仓库变化 |
| 项目用途 | 个人博客 |

**仓库操作边界：**本项目的所有 GitHub 操作只针对 `mymsnn/mymsnn.github.io`。不得将 `myogg` 名下的其他仓库当作本项目目标。

### 1.2 备份仓库

用户已建立私有备份仓库：

- `mymsnn/mymsnn.github.io-backup`

**待核实：**备份仓库当前是否存在、是否仍为私有、最近同步时间、与主仓库的文件及提交差异。本次没有验证同步状态。不得假定备份已经同步。

### 1.3 其他仓库的区分

此前对话中出现过 `myogg/moon`、`myogg/astro` 等其他项目仓库。它们不是本项目的主仓库。除非用户明确提出跨仓库参考或操作，否则不得对它们执行本项目的写入操作。

---

## 2. 技术与主题结构

### 2.1 已确认的技术基础

从主仓库 `_config.yml` 读取确认：

- 静态站点生成器：Jekyll
- 主题：Minima（配置项为 `theme: "minima"`）
- 插件：`jekyll-feed`、`jekyll-sitemap`
- RSS 配置：`rss: rss`
- Kramdown 的语法高亮选项中设置了 `disable: true`
- 文章默认标签：`Other`

因此，本项目是 Jekyll + Minima，不是 Astro 项目。

**待核实：**Minima 的准确版本、依赖锁定方式、主题代码实际来源，以及 GitHub Pages 构建环境使用的 Jekyll 版本。本次未找到 `Gemfile`，不能据此推断依赖版本。

### 2.2 已读取确认的文件

| 文件路径 | 已确认用途或内容 |
|---|---|
| `_config.yml` | 网站标题、作者、描述、社交账号配置、Minima 主题、插件及文章默认值 |
| `_includes/head.html` | 页面 head；加载 Minima 的 `/assets/main.css`、自定义 CSS、feed 元信息和 highlight.js |
| `css/override.css` | 仓库自定义字体、颜色、文章排版、首页列表、导航等样式 |
| `_layouts/post.html` | 仓库自定义文章布局；输出标题、日期、作者、分享区域、正文及前后篇导航 |
| `_includes/navlinks.html` | 文章上一篇/下一篇导航；无前后篇时链接到 `archive.html` |
| `_includes/sharelinks.html` | 文章分享区域及相关图标、分享链接 |
| `README.md` | 英文项目说明页面，使用 `layout: page`，固定路径 `/readme.html` |
| `link.md` | 已于 2026-11-24 删除；不再作为站点页面 |
| `_posts/2026-11-21-zuoge-youyisi-de-ren.md` | 当前已核实的开篇文章 |

### 2.3 主题加载关系（已知部分）

1. `_config.yml` 声明使用 Minima。
2. `_includes/head.html` 加载 `/assets/main.css`，这是 Minima 样式入口；同时加载 `/css/override.css`。
3. `_layouts/post.html` 是仓库自定义文章布局，并包含分享区域和文章导航。
4. `_includes/sharelinks.html` 与 `_includes/navlinks.html` 分别负责分享和前后篇导航。
5. Minima 主题自身提供的默认布局、页眉、页脚等具体文件，尚未在本仓库路径中完整核实。

**结构保护原则：**基础主题与仓库自定义样式/布局分开看待。保留 Minima 及现有页面、导航和自定义功能；未经用户确认，不替换主题、不整体重建主题，也不删除已有结构。

### 2.4 尚未核实或发现路径差异的文件

以下路径的 GitHub 文件读取请求返回 404；这只说明这些确切路径未找到，不代表相应功能一定不存在：

- `_layouts/default.html`
- `_layouts/page.html`
- `index.html`
- `archive.html`
- `.github/workflows/jekyll.yml`
- `Gemfile`
- `CNAME`

特别注意：`_includes/navlinks.html` 中确实引用了 `archive.html`，但本次在仓库根目录读取 `archive.html` 返回 404。需要检查完整目录树，确认是否有其他归档页面路径、主题提供的页面或链接失效情况。不要在核实前自行创建、删除或改写页面。

另外，`_includes/head.html` 引用了 `/js/highlightjs/` 下的样式和脚本；目录具体文件清单尚未完整检查。

---

## 3. 已完成修改记录

以下记录来自 GitHub 主仓库提交历史。时间同时列出 GitHub 返回的 UTC 时间及对应北京时间（UTC+8）。

| 北京时间 | 提交说明 | Commit SHA |
|---|---|---|
| 2026-11-21 16:02:35 | Clear repository contents and start fresh（清空仓库内容，重新开始） | `939d9dc41e7c7b7d366d1200ceb0bf04ed87cd10` |
| 2026-11-21 16:07:32 | Restore site files without old posts（恢复网站文件，不恢复旧文章） | `b5dd65435edcccbab8ee028e992e8898cab89717` |
| 2026-11-21 16:18:34 | Add opening post: 做个有意思的人（添加开篇文章） | `1a18908893f2c53b4a79c6e548fa929074a3ccdb` |
| 2026-11-21 16:29:06 | Improve typography and reading layout（改进字体与阅读排版） | `620e1896c9f3f89732af3056356b948d2800cce8` |
| 2026-11-21 16:29:12 | Load site-wide typography styles（加载全站字体样式） | `4c53c5f71ef5f44d1503a95a455fd21cae743f20` |

相关提交链接：

- https://github.com/mymsnn/mymsnn.github.io/commit/939d9dc41e7c7b7d366d1200ceb0bf04ed87cd10
- https://github.com/mymsnn/mymsnn.github.io/commit/b5dd65435edcccbab8ee028e992e8898cab89717
- https://github.com/mymsnn/mymsnn.github.io/commit/1a18908893f2c53b4a79c6e548fa929074a3ccdb
- https://github.com/mymsnn/mymsnn.github.io/commit/620e1896c9f3f89732af3056356b948d2800cce8
- https://github.com/mymsnn/mymsnn.github.io/commit/4c53c5f71ef5f44d1503a95a455fd21cae743f20

### 3.1 清理与恢复

提交记录显示，项目经历了清空仓库内容、恢复网站文件（不恢复旧文章）的过程。当前已核实网站配置、布局、样式及 README 项目说明页面等文件存在。About 页面文件此前已不存在；友情链接页面已于 2026-11-24 删除。

用户明确的目标是清理旧文章内容、保留网站主题和结构。不得把“清理文章”扩大解释为“删除主题、图片、导航或页面”。

### 3.2 字体和排版修改

已核实修改涉及：

- `css/override.css`
- `_includes/head.html`

当前 `css/override.css` 中可直接读取到的设置：

| 项目 | 当前代码值 |
|---|---|
| 中文/系统字体优先级 | `MiSans`、`MiSans L3`、系统字体及 sans-serif 回退 |
| 正文字色 | `#292929`（body）；文章正文为 `#303030` |
| 全站基础行距 | `1.75` |
| 桌面文章正文 | `18px` |
| 手机文章正文（宽度不超过 600px） | `17px` |
| 文章正文行距 | `1.9` |
| 文章最大宽度 | `720px` |
| 桌面文章标题 | `2.35rem` |
| 手机文章标题 | `1.85rem` |
| 首页文章列表 | 去掉圆点，增加底部分隔线 |
| 正文图片 | 最大宽度 100%，高度自适应 |

**待核实：**CSS 已将 MiSans 列为优先字体，但是否实际下载、安装或由浏览器加载成功，尚未验证。不能仅凭 CSS 声明认定字体已经在所有设备生效。

### 3.3 主题与设计方向

用户已明确：

- 保持当前主题，不换成另一套主题。
- 希望借鉴上游主题值得参考的风格和设计。
- 当前阶段重点是重新写内容，而不是反复更换主题。
- 代码修改尽量克制，优先借鉴字体、排版等细节。
- 不因为“可以改”就随意改动。


### 3.4 网站名称与副标题（2026-11-22）

用户确认网站采用以下名称：

- 网站主标题：**好柿花生**
- 网站副标题：**做一个有意思的人**

已修改文件：`_config.yml`

- `title` 曾于 2026-11-22 先调整为“江山易改”，随后通过提交 `c70e7ead6800383d6f64cae2fa3e17e2375d0d48` 正式更名为“好柿花生”。
- `description` 从原有描述调整为“做一个有意思的人”，作为 Minima 主题的站点描述/副标题。
- 未修改主题、文章、图片、导航、页面结构或其他配置项。

配置修改提交：`72cbfe31d7b8337be2f12ae6231ae73a08f55b40`。

**部署状态：待核实。** 已将修改推送到 `master`；GitHub Pages 是否已完成本次构建及网站是否已显示新名称，需要检查 Actions 和实际网站后确认。

---

## 4. 文章记录与写作约定

### 4.1 文章目录和格式

当前已核实的文章路径：

`_posts/2026-11-21-zuoge-youyisi-de-ren.md`

从该文章确认的 Front Matter 格式：

```yaml
---
title: "文章标题"
date: 2026-11-21
---
```

文章正文使用 Markdown。

配置文件为所有 post 设置了默认标签 `Other`。目前没有证据表明摘要或 tags 是每篇文章必须手动填写的字段，因此不将其列为强制要求。

**待核实：**是否存在其他文章命名规范、时区约定、摘要要求或额外 Front Matter 字段。

### 4.2 写作方向

博客是个人记录空间，内容方向包括：

- 日常生活与心境；
- 个人经历和回忆；
- 读书、音乐及兴趣；
- 生活见闻和观察；
- 那些值得记录、不愿遗忘的事情。

不必追热点，不必迎合他人，也不为了更新而更新。

### 4.3 文章编辑约定

1. 保留作者原意和完整原文。
2. 未经允许，不擅自删段、删句或缩写。
3. 未经允许，不改变文章立意和叙述视角。
4. 润色必须尊重原文，不擅自添加作者没有提供的经历或事实。
5. 用户要求整理成文档时，保留其确认过的内容。
6. 修改已发布文章前，先说明修改方案；重要改动必须征得用户确认。
7. 任何文章修改都要保留可追溯的原文记录。

### 4.4 当前开篇文章原文

**标题：做个有意思的人**

**文件：** `_posts/2026-11-21-zuoge-youyisi-de-ren.md`

**GitHub 文件链接：**  
https://github.com/mymsnn/mymsnn.github.io/blob/master/_posts/2026-11-21-zuoge-youyisi-de-ren.md

以下为从 GitHub 当前文件读取的正文原文，作为档案保存：

> 有些事情，做着做着就放下了；有些地方，走着走着又想回来。
>
> 这个博客其实已经存在很久了。以前写过一些东西，也折腾过不少页面和功能。后来文章越来越少，网站也渐渐安静下来。偶尔想起，才发现自己已经很久没有认真坐下来写点什么了。
>
> 前些日子，我把这里的旧文章清理了一遍。
>
> 不是觉得过去写得不好，也不是想把曾经的自己抹去。只是觉得，一个地方如果很久没有打理，不如收拾干净，重新开始。
>
> 人到了一定年纪，慢慢会发现，生活其实没有那么多惊天动地的大事。每天上班、下班，吃饭、睡觉，偶尔遇到一点开心的事，也会碰上一些不顺心的事。日子就这样一天天过去。
>
> 但我还是觉得，生活应该有点意思。
>
> 所谓有意思，不一定是做出什么了不起的事情，也不一定要活得多么精彩。可能是读到一本喜欢的书，听见一首熟悉的歌，想起一段很久以前的往事；也可能只是某个普通的下午，突然有了一个想法，想把它记下来。
>
> 网络上的地方很多，热闹的地方也很多。但我还是想留一个属于自己的小角落。
>
> 不必追赶热点，不必迎合谁，也不必为了更新而更新。想写的时候就写几句，想记录的时候就留下一点文字。写生活，写见闻，写那些说不清楚却又不愿意忘记的东西。
>
> 至于以后这里会变成什么样子，现在还不知道。
>
> 至少，从今天开始，它又有了新的内容。
>
> 做个有意思的人，过点有意思的日子。
>
> 这就够了。

文章顶部还包含一张图片，Markdown 图片地址为：

`https://i.134688.xyz/file/1795248988860_Screenshot_20261119_103646_com_android_chrome_CustomTabActivity.webp`

**待核实：**该图片链接目前是否可访问，以及是否已纳入主仓库自身的图片备份。不要擅自替换图片。

---

## 5. 页面、导航及功能保护清单

以下项目已在仓库文件中看到，修改时应保护：

- Minima 基础主题配置；
- 自定义文章布局 `_layouts/post.html`；
- 分享区域 `_includes/sharelinks.html`；
- 上一篇/下一篇导航 `_includes/navlinks.html`；
- 英文项目说明页面 `README.md`（固定路径 `/readme.html`）；
- 自定义样式 `css/override.css`；
- highlight.js 资源引用；
- 文章图片及其他静态资源。

用户明确要求：不得擅自删除文章、图片、导航、页面或主题结构。

**待核实：**完整静态资源目录、图片数量、所有页面及导航入口、移动端菜单行为、主题默认页眉页脚的实际来源。

---

## 6. 部署状态

### 6.1 当前结论

**部署状态：待核实。**

对最新提交 `4c53c5f71ef5f44d1503a95a455fd21cae743f20` 查询 GitHub Combined Status，返回的 status checks 列表为空。

这只说明本次查询没有取得状态检查记录，不代表部署失败，也不代表部署成功。

### 6.2 尚需核实

- GitHub Pages 是否启用；
- Pages 的发布来源（分支/目录或 Actions）；
- 实际部署工作流名称和文件路径；
- 最近一次 Pages 部署记录及结果；
- 网站实际访问域名；
- 最新提交是否已经上线；
- 自定义域名及 DNS 配置；
- 备份仓库同步情况。

本档案不记录未经核实的部署成功/失败结论，也不推测网站域名。

---

## 7. 操作约定

### 7.1 仓库安全（最高优先级）

1. 所有仓库操作前，先确认完整仓库名。
2. 本项目唯一指定主仓库为 `mymsnn/mymsnn.github.io`。
3. 确认当前目标分支；目前已核实为 `master`，后续操作仍需重新检查实际状态。
4. 备份仓库与主仓库严格区分。
5. 不得误操作其他用户或其他项目的仓库。
6. 不得因仓库名称相似而自行判断目标。

### 7.2 修改前确认

1. 修改代码前先检查 GitHub 实际状态。
2. 先向用户说明修改方案、原因、涉及文件及影响范围。
3. 重要修改必须征得用户确认。
4. 用户明确要求直接执行的具体操作，可按其授权范围执行；不得扩大操作范围。
5. 不确定的文件、依赖、部署配置先核实，不靠猜测。
6. 优先小范围、可回退的修改。

### 7.3 内容和结构保护

- 不擅自删除文章、图片、导航、页面或主题文件。
- 不擅自替换 Minima 主题。
- 不擅自改变网站整体结构。
- 不擅自改写用户文章。
- 不把其他仓库的配置或代码直接覆盖到本仓库。
- 不因测试而清理用户未授权删除的分支或文件。

### 7.4 面向 Android 用户的协作方式

用户主要使用 Android 手机，不熟悉代码。操作时应：

- 在授权范围内尽量直接完成 GitHub 操作；
- 避免要求用户手动编辑复杂代码；
- 减少让用户在 GitHub 页面中寻找文件的步骤；
- 需要用户操作时，给出清晰、简短、按步骤的说明；
- 完成后说明修改文件、提交记录和后续状态。

### 7.5 每次重要工作后的记录

每次完成重要修改、文章发布、主题调整或部署工作后，都更新本文件。

每次更新至少记录：

| 档案字段 | 应记录内容 |
|---|---|
| 仓库 | 完整仓库名称 |
| 分支 | 实际操作分支 |
| 修改文件 | 文件路径及具体变化 |
| 提交记录 | Commit SHA、时间、提交说明 |
| 部署状态 | 成功、失败或待核实，并记录证据 |
| 文章记录 | 标题、路径、完整原文或原文变更说明 |
| 主题结构 | 结构、依赖或样式变化 |
| 下一步任务 | 未完成事项及阻塞原因 |

### 7.6 新聊天接续

新聊天开始时，先核对 GitHub 实际状态，再继续工作：

1. 核对主仓库名称和默认分支；
2. 获取最新提交；
3. 检查上次修改的文件；
4. 对照本档案中的文章原文和提交记录；
5. 检查部署状态；
6. 更新本档案中的待办和已完成事项。

接近上下文上限时，主动生成完整交接记录，至少包含仓库、分支、文件修改、提交记录、部署状态、文章原文和下一步任务。

---

## 8. 当前待办事项

### 8.1 已确定的工作方向

- [ ] 完整核对仓库目录树。
- [ ] 核实上游主题的来源、仓库地址及版本。
- [ ] 区分 Minima 提供的文件与仓库自定义文件。
- [ ] 核实 MiSans 字体是否实际加载。
- [ ] 检查手机端和电脑端的实际显示效果。
- [ ] 检查文章分享、上一篇/下一篇导航是否正常。
- [ ] 检查旧文章清理后的页面状态。
- [ ] 确认开篇文章及其图片可正常访问。
- [ ] 检查归档链接与归档页面路径是否一致。

### 8.2 必须核实的信息

| 项目 | 状态 |
|---|---|
| 实际网站域名 | 待核实 |
| GitHub Pages 是否启用 | 待核实 |
| Pages 发布来源及工作流 | 待核实 |
| 最新提交是否部署成功 | 待核实 |
| 上游主题仓库地址 | 待核实 |
| Minima 准确版本 | 待核实 |
| Jekyll 构建环境版本 | 待核实 |
| 完整目录树 | 待核实 |
| 图片和静态资源完整性 | 待核实 |
| MiSans 字体实际加载情况 | 待核实 |
| 手机端/电脑端实际效果 | 待核实 |
| 备份仓库同步状态 | 待核实 |
| 归档页面实际位置及可访问性 | 待核实 |

---

## 9. 档案维护记录

| 日期 | 变更 |
|---|---|
| 2026-11-22 | 先将网站主标题调整为“江山易改”，副标题为“做一个有意思的人”；随后用户将站点更名为“好柿花生”，见提交 `c70e7ead6800383d6f64cae2fa3e17e2375d0d48`。 |
| 2026-11-21 | 建立初始项目档案；记录仓库、分支、主题配置、已读取文件、提交历史、开篇文章原文、写作及操作约定；部署、上游版本和备份同步状态标记为待核实。 |
| 2026-11-22 | 按用户确认，将档案从仓库根目录移动至 `.github/PROJECT-RECORD.md`，完整保留原有档案内容及文章原文；从网站发布根目录移走，避免作为普通 Markdown 页面发布。迁移提交：`e89235f7b42c1b6a47db961ead91f9c83e179a80`。 |

**维护规则：**本文件是项目事实记录，不是愿望清单。只有实际完成并有证据的工作才能从“待办/待核实”更新为“已完成/已确认”。更新本档案本身也必须产生可追溯的 Git 提交。


---

## 10. 新文章记录：四十年，不过一场酒的距离（2026-11-22）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 文章标题：四十年，不过一场酒的距离
- 文章路径：`_posts/2026-11-21-sishi-nian-buguo-yichang-jiu-de-juli.md`
- 图片：沿用用户提供的外部图片地址 `https://i.134688.xyz/file/1795340763073_file_00000000b6e481f6af3daea986c04e45.webp`
- 文章提交 SHA：`3896cb0fd6db402efa5d4a15720728998e40b5ea`
- 文章提交说明：`Add post: 四十年，不过一场酒的距离`
- 本次只新增文章文件，没有修改主题、配置、图片文件、导航或页面结构。
- 日期按用户所述“昨天”记为 2026-11-21。
- 部署状态：待核实；尚未检查本次提交对应的 GitHub Pages 构建和线上显示情况。

### 10.1 用户提交的文章原文（完整保留）

以下保留用户润色前提供的完整正文，作为原文记录；发布版本见上述文章文件。

昨天，和三个初中同学坐在一起，喝了点酒。

本来就是一次再普通不过的聚会，几个人见面，聊聊天，喝几杯酒，说说各自这些年的生活。

聊着聊着，忽然算了一笔时间账。

这一算，竟然整整四十年了。

四十年。

这个数字说出来，自己都有些不敢相信。

当年坐在同一间教室里的几个少年，如今都已经过了知天命的年纪。曾经稚嫩的脸庞，早已被岁月悄悄改了模样。各自走过不同的路，经历不同的生活，有过顺心的时候，也有过不容易的日子。

这四十年里，我们有过多少次擦肩而过，又有多少年没有坐下来好好聊过，恐怕谁也说不清楚。

可真坐到一起，倒也没有多少生分。

聊起当年的学校，聊起那些熟悉的名字，聊起年轻时候的一些事情，仿佛时间一下子退回了从前。

只是酒杯里的我们，早已不是当年的少年。

人这一辈子，大概就是这样。

年轻的时候，总觉得日子很长，以为毕业后的分别不过是暂时的，以为以后还有很多机会见面。等到走过半生才发现，有些同学，有些往事，有些一起度过的时光，早已经成了生命里不可复制的一部分。

昨天没有什么特别的仪式，也没有刻意安排什么感人的话。

就是几个老同学，坐在一起，喝了几杯酒。

但我觉得，这样就很好。

四十年过去了，大家还能坐在一起，认得彼此，说得上话，还能为当年的一些小事笑出声来。

这本身就是一件值得高兴的事。

酒会喝完，聚会也会散场。明天依然要回到各自的生活里，继续忙着那些琐碎而平常的事情。

只是这一晚，值得记下来。

敬曾经的少年，也敬走过四十年岁月的我们。

四十年，不过一场酒的距离。

图片 Markdown 原文：

`![file_00000000b6e481f6af3daea986c04e45.png](https://i.134688.xyz/file/1795340763073_file_00000000b6e481f6af3daea986c04e45.webp)`

### 10.2 发布版本说明

发布版本仅作轻微文字润色，保留原文的叙述顺序、段落脉络和核心表达；图片地址不变。最后一句按用户要求加粗：

**四十年，不过一场酒的距离。**

### 10.3 本次工作后的下一步

- [ ] 检查文章提交后的 GitHub Pages 构建结果。
- [ ] 检查网站是否已显示新文章及图片。
- [ ] 确认部署完成后更新本档案中的部署状态。


### 10.4 部署结果补记（2026-11-22）

文章提交 `3896cb0fd6db402efa5d4a15720728998e40b5ea` 对应的 GitHub Actions 工作流：

- 工作流：Deploy Jekyll with GitHub Pages dependencies preinstalled
- 运行编号：307
- 运行记录：https://github.com/mymsnn/mymsnn.github.io/actions/runs/45009519314
- 最终状态：`completed`
- 结论：`success`

因此，文章提交对应的 Jekyll / GitHub Pages 构建与部署工作流已成功完成。此结论只针对上述文章提交；网站实际页面的外部访问显示尚未单独验证。

档案更新提交 `8c185733fcc0d656d5cebc45cc469c7969a1838a` 触发的工作流运行编号为 308，核对时仍为 pending；该提交只更新本档案，不改变文章内容。


---

## 11. 文章页标题间距调整（2026-11-22）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 用户需求：文章详情页的网站标题与文章标题距离较近，希望增加留白；不需要隐藏网站标题。
- 修改文件：`css/override.css`
- 修改内容：仅为文章容器 `.post` 增加 `margin-top: 24px`，让文章标题整体与上方网站标题/导航区域拉开距离。
- 影响范围：文章详情页；首页、导航、网站标题、文章内容和主题结构均未修改。
- 未修改：`_layouts/post.html`、文章文件、图片及导航文件。
- CSS 提交 SHA：`6f5220177897a327c817b1c1fb72b310067fc4da`
- 部署状态：待核实；需检查该提交对应的 GitHub Actions 工作流。
- 下一步：用户在手机上刷新文章页，确认间距是否合适；如仍显得紧凑，再小幅调整数值。


---

## 12. 文章页网站标题字号与字重调整（2026-11-22）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 用户需求：文章页顶部网站标题缩小字号并取消加粗；首页不变。
- 修改文件：`css/override.css`
- 修改内容：增加文章页专属选择器 `body:has(.post) .site-title`，字号设为 `1.25rem`（约 20px），字重设为 `400`，字间距设为 `0`。
- 影响范围：仅文章详情页顶部网站标题；首页标题、导航结构、文章标题、正文及此前增加的 24px 文章页上边距均保留。
- 本次未修改：文章文件、图片、导航文件和主题结构。
- 样式提交 SHA：`2f2b21de2a52de20487952644d011d68981ec089`
- 部署状态：待核实；需检查本次提交对应的 GitHub Actions 工作流。
- 下一步：部署完成后在手机刷新文章页，确认字号和字重观感。


---

## 13. 现状复核与维护整理（2026-11-24）

本节以 2026-11-24 从 GitHub `master` 实际读取的文件为准；若与旧记录冲突，以当前文件和可核对的提交历史为准。

### 13.1 当前站点名称

- 当前 `_config.yml` 的 `title`：`好柿花生`。
- 当前 `description`：`做一个有意思的人`。
- 更名提交：`c70e7ead6800383d6f64cae2fa3e17e2375d0d48`（Rename site to 好柿花生）。
- 本次仅核对配置，没有修改站点名称或副标题。

### 13.2 当前自定义 CSS 的真实状态

当前 `css/override.css` 仅包含：
- `hr` 的上下边距；
- `.post_navi` 文章前后导航布局及其标签、箭头样式。

需要特别保留以下历史事实：
- 2026-11-21 的提交 `620e1896c9f3f89732af3056356b948d2800cce8` 曾加入 MiSans 字体栈、正文宽度/字号/行距、首页文章列表、标题、引用、图片、表格和代码块样式。
- 2026-11-22 的提交 `6f5220177897a327c817b1c1fb72b310067fc4da` 曾增加文章页顶部留白。
- 2026-11-22 的提交 `2f2b21de2a52de20487952644d011d68981ec089` 曾调整文章页网站标题字号和字重。
- 2026-11-23 的提交 `ce1ac6488903e30756cc5b5da003e3ac54571aa2` 明确执行“恢复原有字体与 CSS 样式”，将上述大段自定义排版规则移除。
- 因此，当前没有 MiSans 自定义字体声明，也没有上述文章排版规则。不得把已移除的样式误记为当前生效配置；未经用户明确要求，不要重新添加。

### 13.3 当前代码高亮配置

当前 `_includes/head.html` 同时加载：
- `/js/highlightjs/styles/github.css`
- `/js/highlightjs/styles/ssms.css`

当前显式加载语言包：
- `plaintext`
- `powershell`
- `tsql`

当前仓库 `js/highlightjs/styles/` 目录可见 `default.css`、`github.css`、`ssms.css`；未发现上游使用的 `mono.css`。本次没有更改代码高亮配置。后续如需调整，先检查实际文章代码块效果并选择单一主题，不能直接引用仓库中不存在的文件。

### 13.4 维护文件整理

- `README.md` 已从遗留的 MkDocs Material 项目徽章改为当前博客项目说明。
- `.gitignore` 保留原有 `_config.yml` 规则，并补充 Jekyll 构建输出和本地缓存忽略规则：`_site/`、`.sass-cache/`、`.jekyll-cache/`、`.jekyll-metadata`、`.bundle/`、`vendor/`。
- 上述维护性修改不改变网站主题、文章、页面、导航或站点配置。

### 13.5 当前待办与风险

- `_includes/navlinks.html` 引用 `archive.html`；仓库中存在 `archive.md`（`layout: page`、标题为 Blog Archive），Jekyll 会将 Markdown 页面构建为 HTML 页面，因此该引用有对应源文件。仍需在部署后点击验证线上归档页。
- `_includes/head.html` 同时加载 `github.css` 和 `ssms.css`。复核两份 CSS 后确认：`github.css` 提供通用代码高亮，`ssms.css` 的选择器限定在 `.language-tsql`，用于 SQL Server T-SQL 专属配色；两者是通用主题加语言专属覆盖，不应误删其中一份。
- 当前 `.gitignore` 仍忽略 `_config.yml`，但该文件已被 Git 跟踪；此规则会影响未来新建/重新跟踪时的行为，暂时保留，后续确认是否仍有必要。
- 当前分支 `master` 未启用保护规则；写入前继续核对分支最新 SHA，避免覆盖他人或并发提交。
- 本次未检查 GitHub Actions 最近一次运行，也未验证网站线上显示，部署状态仍为待核实。


### 13.6 文章日期位置复核（2026-11-24）

- 已重新读取当前 `_layouts/post.html`。
- 日期由 `<time class="dt-published">` 输出，位置紧跟文章 `h1.post-title` 之后，位于作者信息和分享链接之前。
- 当前文章页顺序为：文章标题 → 日期 → 作者（有设置时）→ 分享链接 → 正文。
- 本次没有修改 `_layouts/post.html`，今后进行样式优化时必须保留日期在文章标题正下方的顺序。


# Project Record — mymsnn.github.io

> Last reviewed: 2026-11-24  
> Repository: `mymsnn/mymsnn.github.io`  
> Default branch: `master`

## Latest update — 2026-11-24

### Navigation and README page

- Replaced the repository's Chinese README with an English, visitor-facing site guide.
- Added Jekyll front matter to `README.md` and assigned the page URL `/readme.html`.
- Configured Minima navigation to show `README` and `link` only.
- Removed `about.md`; the old About page is no longer part of the site.
- Kept the existing theme, post layouts, styles, links page, posts, and images unchanged.

**Deployment:** Pending verification. The changes were committed to `master`; the corresponding Pages build and live page have not yet been checked.

## Project facts

- Site title: 好柿花生
- Tagline: 做一个有意思的人
- Repository: https://github.com/mymsnn/mymsnn.github.io
- Generator: Jekyll
- Theme: Minima
- Main content: personal writing about everyday life, memories, observations, technology, and interesting things found online.
- Posts: `_posts/`
- Images: `assets/images/`
- Custom styles: `css/override.css`
- Custom templates and includes: `_layouts/`, `_includes/`

## Working principles

- Keep the Minima theme and the existing visual identity.
- Prefer small, reversible changes over broad redesigns.
- Do not sync or merge the upstream repository wholesale.
- Do not overwrite or delete posts, images, or site features without explicit permission.
- Preserve the post layout, date placement, sharing links, and previous/next navigation.
- Verify deployment before describing a change as live.

## Recent project history

- Site title and tagline were set to 好柿花生 / 做一个有意思的人.
- The original Minima-based design and custom post layout were retained.
- Custom CSS remains in `css/override.css`.
- The About page was already absent when checked.
- The Links page (`link.md`) is deleted.
- The original archive source (`archive.md`) is retained and its navigation entry has been restored alongside README.


---

## 11. 页面导航与英文 README 更新（2026-11-24）

用户要求删除 About 和 Links 页面，并以英文 README 说明博客要点，参考 baotiao 博客的 `CLAUDE.md` 项目说明页。

### 11.1 已完成修改

| 文件 | 修改 |
|---|---|
| `README.md` | 扩充为完整英文项目说明页，保留 Jekyll page front matter 和固定路径 `/readme.html` |
| `_config.yml` | `header_pages` 显示 `archive.md` 和 `README.md`；恢复归档入口，移除 Links |
| `link.md` | 已删除友情链接页面（本次复核仍为 404） |
| `about.md` | 核实仓库中此前已不存在（GitHub 文件读取返回 404），无需再次删除 |

README 当前说明内容包括博客定位、内容范围、站点技术栈、仓库目录、文章写作格式、代码高亮、文章布局与维护原则。原有 `archive.md` 页面一直保留，本次已恢复其顶部导航入口。

### 11.2 提交记录

| 修改 | Commit SHA |
|---|---|
| 扩充英文 README | `8329a79c32e3edb80a703ad7a61ef7ddf816a5da` |
| 导航仅保留 README | `8e47cc689dcaee86309f844d686d5081a35ce847` |
| 删除 Links 页面 | `73690be34f70615f225f26e42d17378ef566caaa` |

### 11.3 部署状态

修改已推送到 `master`。本次尚未检查 GitHub Pages 构建记录或线上页面，因此部署状态：**待核实**。


### 11.4 归档导航恢复（2026-11-24）

- 用户要求删除 Links 页面并恢复原来的归档入口。
- 复核确认：`link.md` 已不存在（GitHub 返回 404）；`archive.md` 原文件仍存在，内容未改动。
- 修改文件：`_config.yml`。
- 将 Minima 的 `header_pages` 恢复为 `archive.md`、`README.md`，顶部导航显示 Archive 与 README，不显示 Links。
- 配置提交 SHA：`ead5044fc12859abf2ea8ad6b4a91c64834513f0`。
- 未修改：归档页面正文、文章、主题、文章布局及其他页面。
- 部署状态：待核实；尚未检查本次提交对应的 Pages 构建和线上导航。

---

## 14. 手机端文章标题字号微调（2026-11-24）

- 用户确认：手机文章页标题略微缩小字号。
- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 修改文件：`css/override.css`
- 修改内容：新增移动端媒体查询（最大宽度 800px），将文章标题 `.post-title` 字号设为 `2rem`，行高设为 `1.2`。
- 影响范围：仅文章详情页标题在移动端的显示；桌面端字号、首页文章列表、日期位置、作者信息、分享区域、正文和主题结构均未修改。
- 未修改：`_layouts/post.html`、文章文件、图片、导航及分享链接。
- CSS 提交 SHA：`050fd6788893fd593eff435cf73b41f4314626c1`。
- 本档案更新提交：待本次写入返回 SHA 后补记。
- 部署状态：待核实；尚未检查对应 GitHub Pages 构建及手机端线上显示。


---

## 15. 深色居中博客头部（2026-11-25）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 用户参考：手机截图中的 Kostya's Lair 头部布局。
- 用户确认采用的方向：深炭黑背景；品牌标识与网站名称居中；左侧三横线菜单；副标题单独居中显示。
- 新增文件：`_includes/header.html`，覆盖 Minima 默认页眉 include，保留 `site.header_pages` 导航循环及复选框式移动菜单交互。
- 修改文件：`css/override.css`，新增深色头部、居中品牌行、橙色菱形/绿色圆点/白色竖条品牌标记、左侧菜单按钮及移动端字号规则。
- 网站名称与副标题继续读取 `_config.yml` 中现有的“好柿花生”和“做一个有意思的人”，没有改动配置。
- 未修改：文章、文章日期顺序、正文、图片、分享链接、前后篇导航、归档和 README 页面内容。
- 提交记录：
  - 新增页眉：`f8be5205898eec378995fe3b5aa07e7eda644de3`
  - CSS 样式：`478169784317ab0bc092702bcd2b82a97597122f`
  - 清理页眉 include 文件头：`e5b45d1bee6e04d8bdc9108a4b690aacfde09fbe`
- 部署状态：待核实；尚未检查 GitHub Pages 构建结果及手机端线上显示。
- 下一步：检查 Pages Actions；构建成功后用手机刷新首页与文章页，重点检查菜单展开、品牌居中和副标题留白。


### 15.1 手机端头部问题修正（2026-11-25）

- 用户提供线上手机截图，发现 Minima 默认 label 样式覆盖菜单按钮，出现白色长条，菜单图标偏右；头部纵向留白也偏大。
- 修改文件：`css/override.css`。
- 修正菜单 label 的浮动、宽高、内边距、边框、圆角和背景，避免继承 Minima 白色按钮外观；菜单定位保持左侧。
- 收紧手机端头部上下 padding、品牌行高度和副标题间距；微调品牌标记尺寸。
- 未修改文章内容、首页列表、文章布局、导航配置和网站名称。
- CSS 修正提交：`d9ae420925da8d6ab4f69f2516bcd774eb35362f`。
- 部署状态：本次修正对应的 Pages 构建待检查。


### 15.2 Minima 导航容器样式冲突修正（2026-11-25）

- 用户反馈上一轮部署后手机端白色长条仍未消失。
- 根因：Minima 移动端默认样式作用于整个 `.site-nav` 容器，设置了白色背景、边框、圆角、右侧定位等；上一轮只重置了内部 label，没有清除容器样式。
- 修改文件：`css/override.css`。
- 对 `.custom-site-header .site-nav` 明确重置左右定位、宽度、内外边距、背景、边框、圆角、阴影和文本对齐，确保菜单容器只按左侧三横线按钮的实际宽度显示。
- CSS 修正提交：`273213ae12ef5454802f7fb0604d78b148620de6`。
- 部署状态：待检查对应 GitHub Pages Actions。


### 15.3 手机端头部字号与图标微调（2026-11-25）

- 用户确认白色导航条问题已解决，并反馈网站标题字体、品牌标记和菜单图标相对原版偏大。
- 修改文件：`css/override.css`。
- 手机端网站标题由 1.65rem 调整为 1.5rem，字重由 600 降为 500。
- 品牌标记整体缩小：白色竖条、橙色菱形和绿色圆点均收窄/缩小。
- 菜单三横线由 28px × 3px 调整为 24px × 2px，按钮点击区域仍保留。
- 副标题由 1.05rem 调整为 1rem。
- 未修改布局结构、导航交互、文章列表或文章内容。
- CSS 提交：`9a693f2cc1b03b2d38609cdfa894083c60808c87`。
- 部署状态：待核实对应 GitHub Pages Actions。


### 15.4 参考图比例二次校准（2026-11-25）

- 重新查看本轮最初上传的 Kostya's Lair 手机截图（692 × 1536）及用户博客截图，按参考图的品牌区比例继续缩小。
- 修改文件：`css/override.css`，仅调整手机端（max-width: 600px）：
  - 网站标题 1.5rem 调整为 1.3rem，字重 400。
  - 品牌标记高度 44px 调整为 37px，竖条/菱形/圆点同步缩小。
  - 菜单三横线宽度 24px 调整为 21px，间距略收窄。
  - 副标题 1rem 调整为 0.9rem。
- 保留菜单点击区域、居中品牌行、左侧菜单位置、深色背景和导航交互。
- CSS 提交：`4cb3e50a520e3ab3afd7cc5e0b56a865733f9882`。
- 部署状态：待核实 GitHub Pages Actions。


### 15.5 副标题改为英文（2026-11-25）

- 用户确认将网站副标题由“做一个有意思的人”改为英文表达。
- 网站标题保持“好柿花生”不变。
- 修改文件：`_config.yml`。
- 新副标题：`Be an Interesting Person.`
- 未修改页眉布局、头部样式、文章内容、导航或其他配置。
- 配置提交：`d10d644fda70f81bc144c00690c84fd13af68c1d`。
- 部署状态：待核实；需检查本次提交对应的 GitHub Pages Actions 结果及线上显示。


### 15.6 网站标题旁增加柿子图标（2026-11-25）

- 用户澄清：希望后续讨论的是首页文章列表标题字号；本次先只添加网站名称旁的柿子图标供预览，暂不调整首页文章标题字号。
- 修改文件：`_includes/header.html`、`css/override.css`。
- 在网站名称“好柿花生”右侧添加原创内嵌 SVG 柿子图案，橙色果实、绿色叶片；桌面端 28px，手机端 21px。
- 不修改网站标题、副标题、首页文章标题字号、文章内容、导航或其他页面。
- 页眉提交：`c630223e9dc6197108cf130e7cd6e7bb5e4a60b0`。
- CSS 提交：`4b03c7b6046ba1219d66e9eeeea764dc51e89ddf`。
- 项目记录提交：待本次写入返回 SHA 后补记。
- 部署状态：待核实；需检查对应 GitHub Pages Actions，并由用户查看线上效果。

### 3.5 页眉柿子图标调整（2026-11-25）

用户认为首次添加的柿子图标效果不理想，要求更换。已在 `_includes/header.html` 中替换 SVG 图形：改为更简洁的圆润橙色果实、单片绿色叶子和简化果蒂；保留原有图标尺寸、颜色样式类、标题位置及页眉布局。未修改首页文章标题字号，也未改动其他页面或文章。

- 修改文件：`_includes/header.html`
- 代码提交：`1d246ed22cf13d1c1cb80d3fa33d909b668d3498`
- 部署状态：待核实。

### 3.6 页眉图标改为图钉与书本（2026-11-25）

用户明确要求不要保留原来的柿子图片/图形，改用其提供的两个图标：📌 📚，放在站点主标题「好柿花生」后面。已删除页眉中的柿子 SVG，并清理对应柿子 CSS，改为直接使用图钉与书本符号；保留标题、字号、位置、英文副标题和其他页眉布局。

- 修改文件：`_includes/header.html`、`css/override.css`
- 页眉 HTML 提交：`06929d930e60224c85fe6a2ff13fea4e6a41c83e`
- 图标样式提交：`82b669d82d2d4006c133b46ecf443d5dd6efd2e7`
- 部署状态：待核实。

### 3.7 手机端网站标题字号微调（2026-11-25）

用户要求将页眉主标题“好柿花生”字体再放大一号。当前手机端标题为 1.3rem，桌面端为 2rem，本次仅将手机端网站标题字号从 1.3rem 调整为 1.4rem；不改变图钉/书本图标、副标题、品牌标记、菜单或首页文章标题字号。

- 修改文件：`css/override.css`
- CSS 提交：`8d5e0a03d1119c36f9d9630acf50cdd0e0f1525b`
- 部署状态：待核实。

### 3.8 首页文章列表标题字号微调（2026-11-25）

用户要求将首页文章列表中的文章标题字体缩小一号。本次仅针对首页 `.home .post-list .post-link` 设置字号为 1.4rem，覆盖 Minima 默认文章列表标题字号；不影响文章详情页标题、页眉主标题、日期、摘要及其他页面。

- 修改文件：`css/override.css`
- CSS 提交：`ba83a7ff60b3c14df920240fe4b8f17ed78257d8`
- 部署状态：待核实。


---

## 16. 首页标签链接与文章分享按钮整理（2026-11-25）

### 16.1 首页标签显示与跳转

- 用户希望首页文章列表中的标签不再带井号，外观更轻、更简洁，并且每个标签都可以点击。
- 新增 _layouts/home.html，基于 Minima 2.5.1 首页布局，仅在文章日期与标题之间增加标签链接；保留原有文章列表、标题链接、RSS 入口及摘要逻辑。
- 标签显示使用文章 Front Matter 中的原始 tag 名称，不显示井号；点击后跳转至归档页对应标签分组。
- 修改 archive.md：为每个标签分组标题添加与 Jekyll slugify 一致的锚点，确保首页标签链接可以定位到该标签下的文章列表。
- 修改 css/override.css：标签使用小号浅灰文字、轻微间距，悬停时显示下划线；不使用醒目的彩色胶囊样式。
- 不修改文章的 Front Matter、正文标签文字、文章内容、文章日期和主题配置。
- 相关提交：
  - 新增首页布局：b941c34d5f6f0a00d2e40e9a01f64bb468a884d2
  - 归档标签锚点：d3e10ccd305eacfacec54107d528fec633288d99
  - 修正首页标签链接地址：53eab9b77a9c8659c8aa3e2dce88db48fd1910fd
  - 标签样式：4d026550dc1deaef72e43e9c2ac2ea1a8787a64f

### 16.2 文章页分享按钮整理

- 用户指出文章页分享区域仍包含已停用的 Google+。
- 修改 _includes/sharelinks.html：删除 Google+ 按钮及对应样式；将原 Twitter 鸟图标替换为 X 图标，并更新按钮标题为 “Share this on X”。
- 保留 Facebook、LinkedIn 和邮件分享；分享区域仍位于文章日期/作者信息之后、正文之前。
- 分享按钮提交：249ac25ec3678e799433c0b88d8fd85aff1c7b0e。

### 16.3 部署状态

- 上述修改均已提交到 master。
- GitHub Pages 构建与线上首页标签点击、归档锚点及文章页分享按钮尚待核实；在 Actions 成功并检查线上页面前，不标记为已部署。


---

## 17. 标签位置纠正：仅显示在文章页（2026-11-25）

上一节 16.1 将标签错误地放到了首页文章列表。用户明确指出标签应显示在文章详情页，而不是首页。现已纠正：

- `_layouts/home.html`：移除首页文章列表中的标签输出，恢复为日期后直接显示文章标题；首页不显示标签。
- `_layouts/post.html`：在文章页标题及日期/作者信息之后、分享按钮之前显示该篇文章的标签。
- 标签不带井号，采用小号浅灰文字；每个标签可点击，跳转至 `archive.html` 对应标签锚点。
- `css/override.css`：删除首页标签样式，改为仅作用于文章页 `.post-header .post-tags` 的样式。
- 保留 `archive.md` 中的标签锚点，供文章页标签链接使用。
- 未修改文章内容、Front Matter、首页文章标题字号、文章日期顺序、分享按钮及导航。

### 修改提交

- 移除首页标签：`5b390fa9d95d92a1d1fe4fcfd3dda9cd633ef553`
- 文章页显示标签：`362a026cf3d300c44116639ecd00d3884b82cde3`
- 标签样式限定文章页：`72ef783cf0a53ff4033130d92d7288643c455847`

部署状态：待检查 GitHub Pages 构建及线上首页/文章页效果。此前第 16.1 节关于“首页显示标签”的记录已被本节纠正；实际目标是文章页显示标签。


---

## 18. 修正文章底部井号标签（2026-11-25）

用户明确指出，目标是文章正文最末尾、分隔线下方原有的 `#Telegram #BotAPI #机器人 #更新` 这类文字标签；不是在文章顶部新增或移动一组 Tags。

- `_layouts/post.html`：删除标题/日期区域误加的顶部标签展示；保留文章标题、日期、作者、分享区域和正文顺序。增加轻量脚本，只识别正文最后一个由井号标签组成的段落，将每个原标签转换为保留井号的独立链接。
- `css/override.css`：移除此前误加的顶部标签样式；为正文末尾标签链接增加 flex 换行布局，横向间距 16px、纵向间距 10px，避免标签挤在一起。
- `_posts/2026-11-24-telegram-bot-api-10-5.md`：将 Front Matter 中的 `Bot API` 统一为 `BotAPI`，使截图中的 `#BotAPI` 对应归档标签锚点。
- `_layouts/home.html` 当前已无首页标签输出，本次未改动首页文章列表。
- 未改动文章正文的标签文字、分享按钮、文章导航和其他文章内容。

提交记录：
- 文章布局：`6ec6a0fa5ba73a6e62896cab892321c61648519f`
- 标签间距样式：`4128cb943a75207a0a068faf82ae18fb3ec843e6`
- Telegram Bot API 10.5 标签名：`c59eb5c81f77acf9a479718ed67ff755e55a9503`

部署状态：待核实 GitHub Pages 构建及线上文章效果；需确认标签链接显示、点击目标和窄屏换行表现。


### 18.1 文章模板修改未生效后的再次修正（2026-11-25）

- 用户反馈线上“没变”后，重新读取 `master` 发现上一轮对 `_layouts/post.html` 的更新实际未写入：顶部标签块仍存在，正文末尾标签处理脚本也不存在。
- 本次重新完整覆盖 `_layouts/post.html` 并立即回读核实：已删除文章顶部 `page.tags` 展示块；在共享文章正文模板中加入末尾井号标签识别与链接转换脚本。
- 新提交：`7783fe6b0c2228441ee9b9a0366f92d257a84252`。
- 本次回读确认源文件内容正确；GitHub Pages Actions run `45624445245` 已排队，尚未构建完成，线上效果仍待核实。


---

## 19. 新文章：全球珊瑚礁正在衰退，海洋升溫讓復原時間愈來愈短（2026-11-25）

- 倉庫：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 文章標題：全球珊瑚礁正在衰退，海洋升溫讓復原時間愈來愈短
- 文章路徑：`_posts/2026-11-25-global-coral-reef-decline.md`
- 文章提交 SHA：`411f04e32fb825bd7c6e520c6a6c58195a994563`
- 日期：2026-11-25。
- 語言：保留使用者提供的繁體中文原文；僅整理 Markdown 標題、段落與刪除重複圖說及頁面廣告殘留字樣，沒有翻譯成簡體中文。
- 圖片使用使用者提供的兩個原始外部連結，按文章內容放置：
  1. `https://i.134688.xyz/file/1795613858483_2026092146835965.webp`
  2. `https://i.134688.xyz/file/1795613864848_2026092147743849.webp`
- Front Matter 標籤：珊瑚礁、海洋暖化、氣候變遷、生物多樣性；文末保留井號標籤。
- 發布正文完整內容保存在上述文章檔案中；本記錄以文章檔案作為完整發布版本的唯一準據。
- 本次沒有新增圖片到倉庫，也沒有修改主題、頁面、導航、CSS 或其他文章。
- 部署狀態：待核實；文章已提交至 `master`，尚待檢查 GitHub Pages Actions 與線上文章、圖片顯示。

- 後續校正：回讀文章時發現兩個 Markdown 圖片連結的結尾括號誤用了全形字元，已修正為標準 Markdown 括號；修正提交：`3fa24f8529d1c74eeb4b5c963cb86a966988822d`。回讀確認兩個圖片語法均正確。
- 最新文章提交對應 Pages Actions run `45625856877`，核對時為 `pending`；文章與圖片尚未確認部署到線上。


---

## 20. 新文章：1Password 确认安全事件（2026-11-26）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 文章标题：1Password 确认安全事件：部分客户账户信息遭窃，保险库未受影响
- 文章路径：`_posts/2026-11-26-1password-security-incident.md`
- 文章提交 SHA：`b8d90b11a1cc1627ea3c675138bc97178bb0466d`
- 日期：2026-11-26。
- 内容依据：1Password 官方 2026-11-25 安全事件公告（https://1password.com/blog/update-on-nov-2026-security-incident）。
- 文章整理：简体中文，按事件经过、受影响信息、未受影响内容、公司措施和用户建议分节；明确补充官方公告列出的公开密钥、SRP 参数及部分邮件链接令牌，并说明这些信息不能单独用于登录或账户恢复。
- 图片：本次用户未提供图片，文章未添加未经确认的配图。
- 未修改：主题、布局、CSS、导航、配置、首页及其他文章。
- 完整发布正文保存在上述文章文件中，作为发布版本的唯一准据。
- 部署状态：文章已提交到 master；尚待核实 GitHub Pages 构建及线上页面。


---

## 21. 新文章：古城慢行（2026-11-26）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 文章标题：古城慢行
- 文章路径：`_posts/2026-11-26-gucheng-manxing.md`
- 文章提交 SHA：`53bafaa47c2568c6920becd57dab33b2b61a0fd6`
- 日期：2026-11-26。
- 内容：简短的古城漫步随笔，记录老街、青石板路、临水木屋、鲜花与蓝天；不添加未经确认的具体地名或行程信息。
- 媒体校正（2026-11-26）：用户指出此前提供的视频链接有误，已从文章中删除整段 MP4 视频嵌入；保留原有 23 张 WebP 图片及其 CDN 地址。未删除或修改 CDN 上的视频文件本身，也未将媒体文件复制进仓库或重新上传。
- 标签：日常、旅行、随拍；文末保留井号标签，沿用当前文章页标签链接处理方式。
- 完整发布正文及保留的 23 张图片地址保存在上述文章文件中，作为本次发布版本的唯一准据。
- 未修改：主题、布局、CSS、导航、配置、首页及其他文章。
- 视频删除修正提交 SHA：10d5b2d5fa13481c354d325fb90e79f94c6b1451。
- 部署状态：视频删除修正已提交到 master；尚待核实 GitHub Pages 构建及线上文章、图片显示。
- 撤稿记录（2026-11-26）：用户要求删除《古城慢行》，已从 `_posts/2026-11-26-gucheng-manxing.md` 删除该文章；删除提交 SHA：`26056c9daf7a8a23989eefeffff8eadfe2d5b416`。本条保留发布历史记录，不代表文章仍在线。


---

## 22. 新文章：Cloudflare Workers 免费计划开放邮件发送（2026-11-26）

- 仓库：`mymsnn/mymsnn.github.io`
- 分支：`master`
- 文章标题：Cloudflare Workers 免费计划开放邮件发送
- 文章路径：`_posts/2026-11-26-cloudflare-workers-email-sending-free.md`
- 文章提交 SHA：`ef1737ed5d0680a264150a5d4e9d973207d8c5bf`
- 日期：2026-11-26。
- 内容依据：用户提供的 Cloudflare 官方更新说明（https://developers.cloudflare.com/changelog/post/2026-11-24-email-sending-workers-free/）。
- 文章内容：介绍 Email Sending 在 Workers Free 计划上线、可通过 Workers 绑定/REST API/SMTP 向已验证地址发送邮件，以及向任意收件人发送邮件需要 Workers Paid 计划。
- 标签：Cloudflare、Workers、邮件服务、开发工具；文末保留井号标签。
- 图片：用户提供了一张 Cloudflare Email Sending 公告配图；本次文章未嵌入该图片，因为当前 GitHub 文件写入流程未能将上传图片作为二进制文件提交。文章正文和官方文档链接已发布。
- 未修改：主题、布局、CSS、导航、配置、首页及其他文章。
- 部署状态：文章已提交到 master；GitHub Pages 构建及线上页面仍待核实。
