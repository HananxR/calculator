
> **This part of the content comes from `install.md`**

________________________________________________________________ 

# Installation Guide

## 📦 Installation Guide: MkDocs and Plugins

This guide will help you install **MkDocs** and essential plugins to generate beautiful documentation directly from your Python code.

---

## 🧰 Prerequisites

Make sure you have Python (version 3.7 or above) and `pip` installed:

```bash
python --version
pip --version
```

---

## 🚀 Installation Steps

### 1. Install MkDocs

```bash
python -m pip install mkdocs
```

Check it's working:

```bash
mkdocs --version
```

---

### 2. Install `mkdocstrings` Plugin (with Python support)

```bash
python -m pip install "mkdocstrings[python]"
```

This plugin **auto-generates documentation** from Python source files and supports several popular docstring styles:

---

### ✅ Supported Docstring Styles (with Examples)

#### 📘 1. Google Style

```python
def add(x: int, y: int) -> int:
    """Add two integers.

    Args:
        x (int): First number.
        y (int): Second number.

    Returns:
        int: The sum of x and y.
    """
    return x + y
```

---

#### 📗 2. NumPy Style

```python
def add(x: int, y: int) -> int:
    """
    Add two integers.

    Parameters
    ----------
    x : int
        First number.
    y : int
        Second number.

    Returns
    -------
    int
        The sum of x and y.
    """
    return x + y
```

---

#### 📙 3. reStructuredText (reST) Style

```python
def add(x: int, y: int) -> int:
    """
    Add two integers.

    :param x: First number.
    :type x: int
    :param y: Second number.
    :type y: int
    :return: The sum of x and y.
    :rtype: int
    """
    return x + y
```

These formats are all rendered cleanly when using `mkdocstrings`.

---

### 3. Install the Material Theme

```bash
python -m pip install mkdocs-material
```

Enable it in `mkdocs.yml`:

```yaml
theme:
  name: material
```

---

## ✅ Done!

Now run your documentation site locally:

```bash
mkdocs serve
```

Visit [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser to preview it.

---

## 📚 Resources

* [MkDocs](https://www.mkdocs.org/)
* [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
* [mkdocstrings](https://mkdocstrings.github.io/)

---

Happy documenting! ✨
