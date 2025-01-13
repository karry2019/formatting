
LatexFormatting is a utility used to format LaTeX and Markdown files.
For English version, please go to branch [main_en](https://github.com/GALVINLAI/formatting/tree/main_en).

# **exe程序下载链接** https://pan.quark.cn/s/1ebd3ea4ca20

# 项目简介


**LatexFormatting** 是一个用于格式化 LaTeX 和 Markdown 文件的实用工具。该工具提供了多种选项来规范化数学公式和文本格式，特别是对由 ChatGPT 生成的 LaTeX 公式进行处理。

简单的演示（新的视频还没做）
[【数学科研向】将 ChatGPT 的回答复制到 Markdown 文件并正常编译数学公式](https://www.bilibili.com/video/BV1HCV7eyEjm/?share_source=copy_web&vd_source=4b19b22e0433c87d80739f9648c6e390)

![窗口界面](https://github.com/GALVINLAI/formatting/blob/main/formatting_88MZxhi81t.png)

## 主要功能

1. **在中日韩字符和英文或数字之间添加空格**  
   默认启用: ✅

2. **将多行空行变成单行空行**  
   默认启用: ✅

3. **行内公式：规范 `$ ... $` 环境**  
   默认启用: ❌

4. **行内公式：规范 `\( ... \)` 环境**  
   默认启用: ❌

5. **行内公式：替换 `\( ... \)` 为 `$ ... $` 环境 【适合ChatGPT的回答】**  
   默认启用: ❌

6. **行间公式：规范 `equation` 环境**  
   默认启用: ❌

7. **行间公式：规范 `$$ ... $$` 环境**  
   默认启用: ❌

8. **行间公式：规范 `\[ ... \]` 环境**  
   默认启用: ❌

9. **行间公式：替换 `\[ ... \]` 为 `$$ ... $$` 环境【适合ChatGPT的回答】**  
   默认启用: ❌

10. **行间公式：替换 `equation` 为 `$$ ... $$` 环境**  
    默认启用: ❌

11. **行间公式：替换 `\[ ... \]` 为 `equation` 环境**  
    默认启用: ❌

12. **行间公式：替换 `$$ ... $$` 为 `equation` 环境**  
    默认启用: ❌

13. **将内嵌在 `equation` 中的 `aligned` 环境变成单独的 `align` 环境**  
    默认启用: ❌

14. **去掉 `align` 和 `equation` 环境中用于不显示tag的 `*` 号**  
    默认启用: ❌

15. **规范 `\item` 格式**  
    默认启用: ❌

16. **规范化各级标题**  
    默认启用: ✅

17. **将 Markdown 的标题等变成 LaTeX 对应物**  
    默认启用: ❌

18. **将 Markdown 的 `**` 包围变成 `\textbf` 环境**  
    默认启用: ❌

19. **将 Markdown 的 `*` 包围变成 `\textit` 环境**  
    默认启用: ❌

20. **去掉所有Markdown特征**  
    默认启用: ❌

21. **规范 `align` 环境**  
    默认启用: ❌

22. **一些小的实用功能**  
    默认启用: ❌

23. **替换 `equation` 为 `equation*` 环境，如果没有 `label`**  
    默认启用: ❌

## 额外说明

1. 可以保存当前复选框情况，下次开启自动复现。
2. 可以批量处理文件夹内所有 `.md` 或 `.tex` 文件。
3. 可以选择自动复制或者手动复制修改后内容。

# 使用方法

## 方法 1：从终端中打开（MAC，或者 WINDOWS 系统皆可）

请确认安装了 `pyperclip` 库
```sh
pip install pyperclip
```
在根目录下运行 `main.py` 会自动打开使用界面。
```sh
python main.py
```

## 方法 2：打包成可执行文件 `formatting.exe` 即可使用。支持多开。（仅限 WINDOWS 系统）

具体打包方法请看下面开发说明。【警告】 该软件可能会被杀毒软件识别并清除，请加入白名单。详情原因参考 [PyInstaller打包的exe被防毒软件报毒怎么办](https://blog.csdn.net/cclbanana/article/details/136010033)

## ⚠️ 注意事项

如果左侧输入框变化时，右侧输出框没有反应。说明出了bug，请关闭重启。

## 如果typora不能正常编译公式

请在 `typora` 偏好设置中，请在 `Markdown` 的设置看是否与下图相同

![typora_markdown_setting](https://github.com/GALVINLAI/formatting/blob/main/typora_markdown_setting.png)


# 开发说明

## 环境要求

- Python 3.x
- 必要的 Python 库：
  - `tkinter` （`tk` 是 python 标准库）
  - `pyperclip`
  - `pyinstaller` （如需另外生成exe文件的话）
  - 持续开发中，缺什么补什么吧

## 项目结构

```plaintext
project/
│
├── main.py                      # 主程序文件
├── icon.ico                     # 程序图标
├── text_processing.py           # 文本处理模块
├── file_operations.py           # 文件操作模块
└── README.md                    # 开发说明（本文件）
```

## 代码结构说明

**`main.py`**：主程序文件，包含 GUI 界面及主要逻辑。

**`text_processing.py`** 和 **`file_operations.py`** 文件包含具体的文本处理和文件操作函数，请根据项目需要进行定义。

## 如何添加自定义的新功能

详见根目录下另一个 `how_add_new_features.md` 文件。

## 构建可执行文件 `formatting.exe` （仅限 WINDOWS 系统）

在 `main.py` 所在的目录下运行如下，使用 `PyInstaller` 创建一个可执行exe文件：
```sh
pyinstaller --onefile --noconsole --name formatting --icon=icon.ico --distpath ./ main.py
```
或者直接在双击 `get_exe.bat`。

如果双击 `get_exe.bat`没有反应，或者错误提示 `'pyinstaller' 不是内部或外部命令，也不是可运行的程序或批处理文件。` 表示系统无法找到 `pyinstaller` 命令，可能是因为 PyInstaller 没有正确安装，或者没有添加到系统的 `PATH` 环境变量中。


### 解决步骤

1. **确认 PyInstaller 是否安装** 打开命令行（CMD）并运行以下命令来确认 PyInstaller 是否已安装：
    ```bash
    pip show pyinstaller
    ```

2. **安装 PyInstaller** 如果没有安装 PyInstaller，可以通过 `pip` 安装它：
    ```bash
    pip install pyinstaller
    ```
    安装完成后，再次运行 `pyinstaller --version` 来验证是否安装成功。

3. **添加 Python 和 Scripts 到 PATH 环境变量**

    如果 PyInstaller 已经安装，但仍然无法找到，可能是因为 `Scripts` 文件夹没有添加到系统的 `PATH` 环境变量中。你可以手动将 Python 的安装目录添加到 `PATH` 环境变量：

    - **找到 Python 安装目录**：通常 Python 安装路径为：

        ```plaintext
        C:\Users\<YourUserName>\AppData\Local\Programs\Python\PythonXX
        ```

        其中，`XX` 是 Python 的版本号。例如，如果是 Python 3.9，那么路径可能是：

        ```plaintext
        C:\Users\<YourUserName>\AppData\Local\Programs\Python\Python39
        ```

    - **添加路径到系统环境变量**：

        1. 在搜索框中输入 `环境变量`，点击 **编辑系统环境变量**。
        2. 在系统属性窗口中，点击 **环境变量** 按钮。
        3. 在 **系统变量** 部分找到 **Path** 变量，选择并点击 **编辑**。
        4. 点击 **新建**，然后添加以下两行（根据你的 Python 安装路径调整）：

            ```plaintext
            C:\Users\<YourUserName>\AppData\Local\Programs\Python\PythonXX\Scripts\
            C:\Users\<YourUserName>\AppData\Local\Programs\Python\PythonXX\
            ```

    - **确认更改**：

        1. 点击 **确定** 保存更改，关闭所有对话框。
        2. 重新打开命令行窗口，运行 `pyinstaller --version` 来验证 PyInstaller 是否可以正常运行。


## 贡献指南

1. Fork 此项目。
2. 创建你的功能分支 (`git checkout -b feature/AmazingFeature`)。
3. 提交你的更改 (`git commit -m 'Add some AmazingFeature'`)。
4. 推送到分支 (`git push origin feature/AmazingFeature`)。
5. 创建一个新的 Pull Request。

## 联系方式

如有任何问题或建议，请联系作者：

- 邮箱：galvin.lai@outlook.com
- GitHub: [GALVINLAI](https://github.com/GALVINLAI/formatting)





