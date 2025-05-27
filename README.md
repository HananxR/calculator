# Python 项目文档示例（基于 mkdocs）

本项目演示了如何使用 [mkdocs](https://www.mkdocs.org/) 构建 Python 项目的文档站点，参考自教程：[Build Python Project Documentation With MkDocs](https://realpython.com/python-project-documentation-with-mkdocs/)。

![image-20250526170210829](https://s2.loli.net/2025/05/26/W16inUea4yVlYGx.png)

## 功能介绍

- 使用 MkDocs 构建静态 HTML 文档站点
- 支持 Markdown 编写文档内容
- 自定义主题、导航、插件等配置
- 支持将文档部署到 GitHub Pages

## 安装与使用

### 0.mkdocs相关库安装

```cmd
python -m pip install mkdocs
python -m pip install "mkdocstrings[python]"
python -m pip install mkdocs-material
```



### 1. 克隆项目

```bash
git clone https://github.com/HananxR/calculator.git
cd <your-repo>
```

### 2. 安装依赖

建议创建虚拟环境：

```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. 启动本地服务预览文档

```bash
mkdocs serve
```

在浏览器中访问 http://127.0.0.1:8000 查看文档。

![image-20250526165243785](https://s2.loli.net/2025/05/26/jD748bO5GPtQiry.png)

## 项目结构

```text
E:.
│  mkdocs.yml
│
├─calculator
│      calculations.py
│      __init__.py
│
├─docs
│      explanation.md
│      how-to-guides.md
│      index.md
│      reference.md
│      tutorials.md
```

- calculator：对应的python packaeg;
- docs和`mkdocs.yml`基于`mkdocs new .`自动生成；
- `docs`中的其他markdown文件为手动创建

## 构建与部署

### 本地构建静态站点

```bash
mkdocs build
```

生成的静态文件将保存在 `site/` 目录中。

### 部署到 GitHub Pages

```bash
mkdocs gh-deploy
```

执行后将自动推送 `site/` 内容到远程仓库的 `gh-pages` 分支。

[GitHub Pages 页面地址示例：](https://hananxr.github.io/calculator/)https://hananxr.github.io/calculator/

## 常用命令

| 命令                | 说明                |
| ------------------- | ------------------- |
| `mkdocs new .`      | 初始化项目          |
| `mkdocs serve`      | 本地启动预览        |
| `mkdocs build`      | 构建静态文档        |
| `mkdocs gh-deploy ` | 推送到 GitHub Pages |

## 教程参考

- [MkDocs 官方文档](https://www.mkdocs.org/)
- [Real Python 教程](https://realpython.com/python-project-documentation-with-mkdocs)
