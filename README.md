<div align="center">

# 📍 File Handling in Python 📍

**A hands-on Jupyter notebook for reading, writing and appending text files in Python**

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Level](https://img.shields.io/badge/Level-Beginner-2ea44f?style=for-the-badge)
![Dependencies](https://img.shields.io/badge/Dependencies-None-lightgrey?style=for-the-badge)

</div>

---

## 📖 Overview

Almost every data science project starts with getting data out of a file. This notebook covers how Python works with **plain text (`.txt`) files** using only the standard library. It goes from opening a file to managing the file pointer, writing new content, and appending to existing files.

Every concept comes with a short, runnable code cell, so you can follow along and experiment.

---

## 🗂️ Project Structure

```
File_Handling_Python/
├── 📓 File Handling in Python.ipynb   # The main tutorial notebook
├── 📁 dataset/
│   └── 📄 file_1.txt                  # Sample 30-line text file used for reading
└── 📘 README.md
```

> 💡 `dataset/new_file.txt` is created automatically when you run the **Writing** section.

---

## 🧠 What You'll Learn

| # | Topic | Key Functions |
|:-:|-------|---------------|
| 1 | 🔐 File access modes | `r`, `r+`, `w`, `w+`, `a`, `a+` |
| 2 | 📥 Reading a whole file | `open()`, `.read()`, `.close()` |
| 3 | 🎯 Moving the file pointer | `.seek()` |
| 4 | 📃 Reading line by line | `.readlines()` |
| 5 | ✨ Safe file handling with context managers | `with open(...) as f` |
| 6 | ✍️ Writing to files | `.write()`, `.writelines()` |
| 7 | ➕ Appending to files | mode `a+` |

---

## 🔐 File Access Modes at a Glance

| Mode | Name | Read | Write | Creates file? | Truncates? | Pointer starts at |
|:----:|------|:----:|:-----:|:-------------:|:----------:|:-----------------:|
| `r`  | Read only       | ✅ | ❌ | ❌ (raises error) | ❌ | Start |
| `r+` | Read & Write    | ✅ | ✅ | ❌ (raises error) | ❌ | Start |
| `w`  | Write only      | ❌ | ✅ | ✅ | ✅ | Start |
| `w+` | Write & Read    | ✅ | ✅ | ✅ | ✅ | Start |
| `a`  | Append only     | ❌ | ✅ | ✅ | ❌ | End |
| `a+` | Append & Read   | ✅ | ✅ | ✅ | ❌ | End |

---

## ⚡ Quick Reference

### 📥 Reading

```python
# Read the entire file
text_file = open("dataset/file_1.txt", "r")
complete_text = text_file.read()

# Reading again returns '' because the pointer is at the end.
# Rewind it with seek():
text_file.seek(0)
text_file.read()

# Jump to any position, e.g. the 300th character
text_file.seek(300)
text_file.read()

text_file.close()
```

### 📃 Line by Line

```python
with open("dataset/file_1.txt", "r") as f:
    lines = f.readlines()

print("No of lines in file is", len(lines))   # → 30
for line in lines:
    print(line)
```

### ✍️ Writing

```python
my_file = open("dataset/new_file.txt", "w")
my_file.write("Data Science is Awesome!")   # returns the number of characters written
my_file.close()

my_file = open("dataset/new_file.txt", "w+")
my_file.writelines(["Line 1", "Line 2", "Line 3", "Line 4"])
my_file.seek(0)
print(my_file.read())   # → Line 1Line 2Line 3Line 4
my_file.close()
```

### ➕ Appending

```python
my_file = open("dataset/new_file.txt", "a+")
my_file.write("Welcome to the python course")
my_file.seek(0)
print(my_file.read())
my_file.close()
```

---

## 💡 Key Takeaways

- 🔁 **The file pointer matters.** After `.read()`, the pointer sits at the end of the file, so a second `.read()` returns an empty string. Use `.seek(0)` to go back to the start.
- 🔒 **Always close your files**, or better, use `with open(...)`, which closes the file for you automatically.
- ⚠️ **`w` and `w+` wipe existing content.** Use `a` or `a+` to add to a file without losing what's already there.
- 🧵 **`.writelines()` doesn't add newlines.** Include `\n` in each string if you want separate lines.
- 🔢 **`.write()` returns a count**: the number of characters written.

---

## 🚀 Getting Started

### Prerequisites

- Python **3.x**
- Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension

No third-party packages are needed. Everything uses Python's built-in `open()`.

### Run It

```bash
# 1. Clone the repository
git clone https://github.com/MrEugeene1/File_Handling_In_Python.git
cd File_Handling_In_Python

# 2. Install Jupyter (if you don't have it)
pip install notebook

# 3. Launch the notebook
jupyter notebook "File Handling in Python.ipynb"
```

Then run the cells from top to bottom. ▶️

---

## 🛣️ Possible Next Steps

- [ ] Handling **CSV** files with `csv` and `pandas`
- [ ] Reading and writing **JSON** files
- [ ] Working with **binary** files (`rb`, `wb`)
- [ ] Handling errors with `try / except FileNotFoundError`
- [ ] Working with paths using `pathlib`

---

<div align="center">

### 👤 Author

**MrEugeene** · [GitHub](https://github.com/MrEugeene1)

⭐ *If you found this helpful, consider giving the repo a star!* ⭐

</div>
