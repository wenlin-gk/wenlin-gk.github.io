## 构建站点site文件

> 借助站点构建工具MKDocs构建。
>
> MKDocs安装使用[参考](https://www.mkdocs.org/)

### 准备工具：安装MKDocs

```
pip install mkdocs
mkdocs --version
```

### 项目结构规范

```sh
project
├── docs
│   └── index.md
└── mkdocs.yml
```

### mkdocs.yml规范

> [第三方theme](https://www.mkdocs.org/user-guide/styling-your-docs/#third-party-themes)<br/>
> [主题效果以及文档入口](https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes)<br/>
> [文档语法](https://squidfunk.github.io/mkdocs-material/extensions/admonition/)

```yaml
site_name: wenlin-gk
repo_name: blog
repo_url: https://github.com/wenlin-gk/summary/tree/master/blog
site_url: https://wenlin-gk.github.io
edit_uri: /wenlin-gk/summary/tree/master/blog/docs
site_author: wenlin

nav:
  - API:
    - HAProxy: HAProxy.md
    - REST-API: REST-API.md
  - CI:
    - git: Git.md
    - zuul: Zuul.md
  - DB:
    - db-server-connect.md
    - mongo+postgres操作.md
    - mysql安装卸载-windows.md
    - mysql常用操作.md
    - mysql各种连接总结.md
    - mysql级联删除.md
  - 文档工具:
    - markdown:
      - github_markdown.md
      - eg1.md
      - eg2.md
    - UML: UML类图几种关系的总结.md
  - 云计算:
    - docker: Docker.md
    - k8s: kubernetes环境搭建.md
  - java: java.md
  - maven: Maven安装与配置.md
  - python: python.md
  - virtualbox: virtualbox-vagrant.md
  - 安全: 安全.md
  - 通用: 通用.md
  - 网络协议: 网络协议.md
  - 环境搭建维护:
    - 构建github-pages.md
    - centos_backup_cfg.md
    - docker_install_cfg.md
    - eclipse_cfg.md
    - linux常用操作.md
    - py2-py3-pip2-pip3安装配置.md
    - ubuntu_backup_cfg.md
    - vnc_cfg.md
    - win10系统配置.md
    - 工具总结.md
    - 环境-运维.md
theme:
  name: material
  custom_dir: custom_theme/
  language: zh
#extra:
#  disqus: wenlin-gk
```

### 本地部署

```sh
# mkdocs自动构建项目框架
mkdocs new $project_name
# 启动
mkdocs serve
# 访问
http://127.0.0.1:8000/
```

## Github自动[部署站点](https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages)

### 开启项目站点部署功能

设置settings -> GitHub Pages开启即可。

### [Push站点文件](https://www.mkdocs.org/user-guide/deploying-your-docs/#organization-and-user-pages)

github站点部署分两类：

1. 项目站点
2. 个人博客站点


## 添加评论功能

> MKDocs支持的第三方评论插件：
>
> Disqus（国外），gitment（国内）
>
> 关键词：github pages mkdocs gitment

### Disqus

注册Disqus，在mkdocs.yaml中[配置](https://squidfunk.github.io/mkdocs-material/getting-started/#disqus)自己的Disqus账号即可。[具体步骤参考](https://github.com/barryclark/jekyll-now/wiki/How-to-add-Disqus-to-your-blog)

mkdocs.yaml

```
nav:
extra:
  disqus: wenlin-gk
```

**问题**：国内无法访问DIsqus，导致评论框显示失败。
