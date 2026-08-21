# 54sy

> 眼泪和坚持一样伟大

**54sy** 是 [wangshuyi111](https://github.com/wangshuyi111) 的个人博客，一份记录软件工程专业学习与成长的进步日志。

在任何一个你没有觉察的时刻——包括现在——通过行动去改变命运的机会，一直都存在。

在线访问：[wangshuyi111.github.io/54sy](https://wangshuyi111.github.io/54sy/)

---

## 三器合璧

<div align="center">
  <a href="https://gohugo.io/">
    <img src="https://raw.githubusercontent.com/gohugoio/gohugoioTheme/master/static/images/hugo-logo-wide.svg?sanitize=true" alt="Hugo" height="60">
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://github.com/D-Sketon/hugo-theme-reimu">
    <img src="https://fastly.jsdelivr.net/gh/D-Sketon/blog-img/icon.png" alt="hugo-theme-reimu" height="60">
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://obsidian.md/">
    <img src="https://i-blog.csdnimg.cn/direct/817a517dfe9a44c68e73be52e4cfd24d.png?x-oss-process=image/resize,m_fixed,h_224,w_224" alt="Obsidian" height="60">
  </a>
</div>

| 项目 | 角色 | 说明 |
|---|---|---|
| [Hugo](https://gohugo.io/) | 静态站点生成器 | 将 Markdown 构建为静态网页，构建速度极快 |
| [hugo-theme-reimu](https://github.com/D-Sketon/hugo-theme-reimu) | 博客主题 | 博丽灵梦风格，由 [D-Sketon](https://github.com/D-Sketon) 创作 |
| [Obsidian](https://obsidian.md/) | 本地编辑器 | 用 Obsidian 打开 `content/post/` 作为仓库，所见即所得地写作 |

---

## 项目结构

```
54sy/
  content/post/             ← Obsidian 仓库根目录
    .obsidian/              ← Obsidian 配置（插件、主题、快捷键、CSS 片段）
    moss_model/             ← 文章模板 + QuickAdd 脚本
    分类目录/               ← 任意创建
      文章名/
        index.md            ← 文章正文
        images/             ← 文章图片
  layouts/                  ← Hugo 主题模板（已适配 Obsidian 语法）
  hugo.yaml                 ← Hugo 配置
  .github/workflows/        ← 自动部署
```

---

## 关于 Hugo

<a href="https://gohugo.io/"><img src="https://raw.githubusercontent.com/gohugoio/gohugoioTheme/master/static/images/hugo-logo-wide.svg?sanitize=true" alt="Hugo" width="400"></a>

[Hugo](https://gohugo.io) 是一个用 Go 语言编写的快速、灵活的静态站点生成器，由 [bep](https://github.com/bep)、[spf13](https://github.com/spf13) 和众多[贡献者](https://github.com/gohugoio/hugo/graphs/contributors) 共同打造。

- 官方网站：[gohugo.io](https://gohugo.io)
- 文档：[gohugo.io/documentation](https://gohugo.io/documentation)
- 开源仓库：[github.com/gohugoio/hugo](https://github.com/gohugoio/hugo)

### Hugo 赞助商

<p float="left">
  <a href="https://www.jetbrains.com/go/?utm_source=OSS&utm_medium=referral&utm_campaign=hugo" target="_blank"><img src="https://raw.githubusercontent.com/gohugoio/hugoDocs/master/assets/images/sponsors/goland.svg" width="200" alt="The complete IDE crafted for professional Go developers."></a>
  &nbsp;&nbsp;&nbsp;
  <a href="https://cloudcannon.com/hugo-cms/?utm_campaign=HugoSponsorship&utm_source=sponsor&utm_content=gohugo" target="_blank"><img src="https://raw.githubusercontent.com/gohugoio/hugoDocs/master/assets/images/sponsors/cloudcannon-cms-logo.svg" width="200" alt="CloudCannon"></a>
</p>

---

## 关于 hugo-theme-reimu

<div align="center">
  <img src="https://fastly.jsdelivr.net/gh/D-Sketon/blog-img/icon.png"/>
  <h3>hugo-theme-reimu</h3>
  <p>💘 博麗 霊夢 💘</p>
</div>

**hugo-theme-reimu** 是一个博丽灵梦风格的 Hugo 主题，由 [D-Sketon](https://github.com/D-Sketon) 从 [hexo-theme-reimu](https://github.com/D-Sketon/hexo-theme-reimu) 迁移而来。

- 主题仓库：[github.com/D-Sketon/hugo-theme-reimu](https://github.com/D-Sketon/hugo-theme-reimu)
- 演示站点：[d-sketon.github.io/hugo-theme-reimu](https://d-sketon.github.io/hugo-theme-reimu)
- 许可证：MIT

### 主题贡献者

[![](https://contributors-img.web.app/image?repo=D-Sketon/hugo-theme-reimu)](https://github.com/D-Sketon/hugo-theme-reimu/graphs/contributors)

### 主题赞助

如果你喜欢这个主题，可以通过 [爱发电](https://afdian.com/a/dsketon) 支持作者 D-Sketon。

---

## 关于 Obsidian

<div align="center">
  <a href="https://obsidian.md/">
    <img src="https://i-blog.csdnimg.cn/direct/817a517dfe9a44c68e73be52e4cfd24d.png?x-oss-process=image/resize,m_fixed,h_224,w_224" alt="Obsidian" width="80">
  </a>
</div>

[Obsidian](https://obsidian.md) 是一个基于本地 Markdown 文件的笔记工具。本项目的 `content/post/` 目录本身就是一个 Obsidian 仓库，你可以：

- 用 Obsidian 直接打开 `content/post/` 作为仓库
- 使用 QuickAdd 脚本一键创建新文章
- 直接粘贴图片，使用 `![[...]]` 语法引用
- 所有 Obsidian 配置（插件、主题、模板、快捷键）随项目一起同步

---

## 许可

本项目博客内容与配置采用 [MIT](LICENSE) 许可。

| 第三方项目 | 许可 |
|---|---|
| [Hugo](https://github.com/gohugoio/hugo) | [Apache 2.0](https://github.com/gohugoio/hugo/blob/master/LICENSE) |
| [hugo-theme-reimu](https://github.com/D-Sketon/hugo-theme-reimu) | [MIT](https://github.com/D-Sketon/hugo-theme-reimu/blob/main/LICENSE) |
| [Obsidian](https://obsidian.md/) | 专有软件（个人使用免费） |

---

*Built with Hugo + hugo-theme-reimu + Obsidian*
