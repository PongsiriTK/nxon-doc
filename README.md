# &lt;Help-Docs&gt;

[//]: # (&lt;!-- 动态徽章示例 --&gt;)

[//]: # (![GitHub release &#40;latest by date&#41;]&#40;https://img.shields.io/github/v/release/your-org/your-repo&#41;)

[//]: # (![GitHub Workflow Status]&#40;https://img.shields.io/github/workflow/status/your-org/your-repo/CI&#41;)

[//]: # (![License]&#40;https://img.shields.io/github/license/your-org/your-repo&#41;)

[English](./README.en.md) | 简体中文

##  项目简介

核心功能是帮助文档的代码仓,并借助 gitlab-runner 和 MkDocs 将 markdown 文件转成静态站点文件

## 🏃‍♂️ 快速开始

### 1. 帮助文档的项目主体及对应的分支

- NXON
    > nxon

### 2. logo 与 favicon
- ./docs/assets/logo.png
  > ![favicon.ico](docs%2Fassets%2Ffavicon.ico)
- ./docs/assets/favicon.ico
  >![logo.png](docs%2Fassets%2Flogo.png)

### 3. [mkdocs.yml](mkdocs.yml) 中修改项目属性的变量
- site_url: https://docs.nxon.ai
- user_name: NXON
- cloud_url: cloud.nxon.ai

### 3. 触发 gitlab-runner,执行 [.gitlab-ci.yml](.gitlab-ci.yml)
>  gitlab-runner 执行完成后生成文件路径: 192.168.10.200:/opt/help-docs/nxon

```bash 
# .gitlab-ci.yml
  - rsync -aztp public/* root@192.168.10.200:/opt/help-docs/nxon
```

### 4. 验证 mkdoc 生成的静态站点文件
