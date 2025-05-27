This part of the project documentation focuses on a
**learning-oriented** approach. You'll learn how to
get started with the code in this project.

> **Note:** Expand this section by considering the
> following points:

- Help newcomers with getting started
- Teach readers about your library by making them
    write code
- Inspire confidence through examples that work for
    everyone, repeatably
- Give readers an immediate sense of achievement
- Show concrete examples, no abstractions
- Provide the minimum necessary explanation
- Avoid any distractions

__________________________________________________________________________
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


当然可以，以下是使用中文编写的标准 Markdown 文档，介绍如何基于 `mkdocstrings` 实现 API 自动文档生成，并结合你的项目结构进行说明：

---

## 使用 `mkdocstrings` 自动生成 API 文档

本部分介绍如何使用 [mkdocstrings](https://mkdocstrings.github.io/) 插件，自动从 Python 源代码中提取并渲染函数和类的文档字符串（docstring），生成清晰易读的 API 参考文档。

---

### 📌 基本原理

在 `reference.md` 文件中看到的文档内容，来自于项目中的 Python 源代码，核心依赖的是 **`mkdocstrings`** 插件。

该插件会自动读取你定义在模块（如 `calculator/calculations.py`）中的 docstring，按指定格式渲染成 HTML 页面。

---

### 📁 示例模块结构

以如下项目结构为例：

```
calculator/
└── calculations.py
```

在 `calculations.py` 文件中，需要使用 Google、NumPy 或 reStructuredText 风格书写清晰的函数说明。

#### ✏️ 示例函数注释：

```python
def add(a: float, b: float) -> float:
    """
    两数相加。

    参数:
        a (float): 第一个数。
        b (float): 第二个数。

    返回:
        float: 相加结果。
    """
    return a + b
```

---

### ⚙️ 操作步骤

#### 1️⃣ 安装插件

使用以下命令安装 `mkdocstrings` 及其 Python 支持模块：

```bash
python -m pip install mkdocstrings[python]
```

---

#### 2️⃣ 配置 `mkdocs.yml`

在 `mkdocs.yml` 中添加如下插件配置：

```yaml
plugins:
  - mkdocstrings
```

你也可以在其中自定义 docstring 样式、是否显示源码等选项。

---

#### 3️⃣ 编辑 Markdown 文件

在文档文件（如 `reference.md`）中，使用如下语法引用模块内容：

```markdown
::: calculator.calculations
```

这条指令会自动渲染 `calculations.py` 中所有带有 docstring 的公共函数和类。

---

### 💡 进阶使用技巧

* 若只想渲染单个函数或类，可使用完整路径：

  ```markdown
  ::: calculator.calculations.add
  ```

* 可在 `mkdocs.yml` 中详细设置显示私有成员、源码块、继承层级等参数。

* 构建文档时，确保代码模块能被正常导入（建议处于同一虚拟环境中，或使用 `PYTHONPATH` 指定路径）。

---

这样配置后，执行 `mkdocs serve` 或 `mkdocs build`，即可实时或最终生成带有 API 自动文档的网页界面。


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