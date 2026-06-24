# cmazhangh.github.io — Hao Zhang 个人学术主页

线上地址:<https://cmazhangh.github.io>

基于 [academicpages](https://github.com/academicpages/academicpages.github.io)
(Jekyll 模板)精简而来,**单页布局**,由 **GitHub Pages 免费托管**,无需自己的服务器。
下面是「我想改 X,该去哪个文件」的维护指南。

---

## 我想改内容 → 去哪个文件?

### 1. 页面正文(研究方向 / 教育 / 经历 / 项目 / 论文)→ `_pages/about.md`
整个主页的所有正文**都在这一个文件**里。语法很简单:

- 一段普通文字 = 一个段落(开头的自我介绍就是这样)
- `标题` 下面紧跟一行 `======` = 一个大节标题
- `- ` 开头 = 列表项
- `**加粗**`、`*斜体*`、`[文字](链接)`

**例:再加一篇论文** —— 在 `Selected Publications` 那节下照着加一行即可:
```markdown
4. **Zhang, H.**, et al. (2026). *论文标题.* **期刊名**, 卷(期). [doi:...](https://doi.org/...)
```

**例:新增一个章节(如 Awards 获奖)** —— 在文件里任意位置加:
```markdown
Awards
======
- **Best Paper Award**, XXX Conference · *2025*
```

### 2. 侧边栏信息(姓名 / 简介 / 单位 / 地点 / 邮箱 / ORCID 等)→ `_config.yml` 的 `author:` 段
找到 `author:` 下面这些字段,填/改即可(留空则不显示):
- `name` 姓名、`bio` 一句话简介、`location` 城市、`employer` 单位、`email` 邮箱
- `orcid` ORCID 链接、`googlescholar` 谷歌学术链接(填上后侧边栏会自动出现对应图标)
- `github` 想把 GitHub 图标加回来,就在这里填用户名

### 3. 换头像 → 直接替换 `images/profile.png`
用你的新照片覆盖这个文件即可(竖版证件照或正方形效果最好),文件名保持不变。

### 4. 换主题配色 → `_config.yml` 里的 `site_theme`
可选:`default` / `air` / `sunrise` / `mint` / `dirt` / `contrast`(当前为 **air** 天蓝)。

### 5. 微调样式(字体大小 / 间距 / 顶栏)→ `assets/css/main.scss` 最底部
文件末尾有一段「Custom refinements」自定义 CSS:字号、章节标题下划线、紧凑侧边栏、
**隐藏顶部导航条**(`.masthead { display: none; }`)等都在这里。想恢复顶部菜单:删掉这行,
再到 `_data/navigation.yml` 里添加菜单项。

---

## 改完怎么发布上线?(任选一种)

**A. 在本地改**(文件在 `/Users/zhanghao/Desktop/Z/cmazhangh.github.io`):
```bash
git add -A
git commit -m "更新内容"
git push
```
约 1 分钟后 <https://cmazhangh.github.io> 自动更新。

**B. 直接在网页上改**:打开
<https://github.com/cmazhangh/cmazhangh.github.io> → 点开要改的文件 →
右上角铅笔 ✏️ → 改完点 "Commit changes",同样自动更新。

---

## 目录说明(精简后)

| 路径 | 作用 | 常改? |
|---|---|---|
| `_pages/about.md` | 主页全部正文 | ⭐ 最常改 |
| `_config.yml` | 全站配置 + 侧边栏信息 + 主题色 | ⭐ 常改 |
| `images/profile.png` | 头像 | 偶尔 |
| `assets/css/main.scss` | 自定义样式(末尾那段) | 偶尔 |
| `_data/navigation.yml` | 顶部菜单(当前为空) | 很少 |
| `_pages/404.md` | 404 页面 | 几乎不动 |
| `_includes/` `_layouts/` `_sass/` `assets/` | 主题引擎 | ⛔ 一般别动 |
| `Gemfile` | 本地构建依赖 | ⛔ 别动 |
| `LICENSE` | 模板开源协议(MIT,需保留) | ⛔ 别删 |
