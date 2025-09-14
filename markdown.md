# <font face = "Times New Roman" font color = "red"> VS Code + Markdown + GitHub </font> <font face = "楷体" font color = "purple"> 个人知识库搭建教程 </font>
## <center><font face ="Yu Gothic" font color = "green" size =5> Intern-8 </font> </center>

- [ VS Code + Markdown + GitHub   个人知识库搭建教程 ](#-vs-code--markdown--github---个人知识库搭建教程-)
  - [ Intern-8  ](#-intern-8--)
  - [一. 准备工作](#一-准备工作)
  - [二. 基本语法](#二-基本语法)
  - [三.图片](#三图片)
  - [四.公式使用(参考Latex语法)](#四公式使用参考latex语法)
  - [五. 目录](#五-目录)
  - [六. 导出PDF](#六-导出pdf)
  - [七.提交到Github](#七提交到github)


## 一. 准备工作

1. **安装 VS Code**  

   [vscode 官网下载地址](https://code.visualstudio.com/)

2. **下载必要的插件**

   > 1. **Markdown All in One**  
   > * 快捷键：使用 `Ctrl+B` 加粗，`Ctrl+I` 斜体等
   > * 智能列表：在列表项后按回车，会自动生成下一项的标记
   > * 自动生成目录

   >2. Markdown Preview Enhanced
   >- 用于增强markdown编辑功能
  
   > 3. Markdown PDF（不推荐）
   > - 用于导出PDF，详情请看[导出PDF](#六-导出pdf)

   > 4. Paste Image
   > - 用于自动插入图片  

3. **创建 `.md` 文档，打开同步预览功能，开始编辑**

---

## 二. 基本语法

1. **标题**
    # 一级标题  
    ## 二级标题  
    ### 三级标题
2. **引用**
   >引用内容
3. **列表**
   1. 无序列表
   - 列表1
   + 列表2
   * 列表3 
   2. 有序列表
   3. 嵌套
   4. TodoList
      - [x] a
      - [ ] b
      - [ ] c
4. **表格**
    | 左对齐 | 居中对齐 | 右对齐 |
    |:-|:-:|-:|
    | a | b | c |
5. **段落**
   - 换行：两个以上空格后回车/空一行
   - 分割线：*** 或者 ---
    ---
    ***
- 字体
| 字体 | 代码 |
|:-:|:-:|
| 斜体 | *斜体* |
| 粗体 | **粗体** |
| 斜粗体 | ***斜粗体*** |
| 删除线 | ~~内容~~ |
| 下划线 | <u>下划线</u> |
| 高亮 | ==高亮== |
6. **代码**
```
# C语言例子
#include<iostream>
using namespace std;
int main(){
    print("hello world");
}
```
`print( "hello wor1d);`

7. **超链接**
- 查找更多使用教程可以[参考网站](https://www.runoob.com/markdown/md-link.html)
- 查看更多使用功能请[点击链接][教程]

## 三.图片
> * 直接将图像存到项目中，比折腾图床更简单、安全和稳定
> * 为了整洁，建议将图像存入固定文件夹，而非与markdown文件并列同级目录
> * 所以虽然`Ctrl+V`就可以直接粘贴图片到同级目录下一起上传，但不推荐

1. **手动方法**：
1. 在项目根目录创建`images`文件夹 (如未创建)
2. 手动复制粘贴图片存入该文件夹
3. 复制**相对路径**并引用
   1. 相对路径即从你当前markdown文件所在位置出发到`images`文件夹的路径。e.g., `./images/test1.jpg`, `../../images/test2.jpg`等
   2. 网络URL则无需下载，直接引用即可加载显示。e.g., `![dojocat](https://octodex.github.com/images/dojocat.jpg)`
4. `git push`的时候把图片和markdown文件都一起提交即可

引用指令: `![图像描述](相对路径)`
- 正常展示
![lion](.\pic\R.jpg)
- 居中展示
<img src="./pic/Lion.webp" alt="lion" style="display: block; margin: 0 auto; width: 200px;"/>

- 如需指定图像大小，可利用该HTML格式指令设置图像宽度：`<img src="./relative/path/to/your/image.jpg" alt="sth" width="200"/>`

<img src=".\pic\lion.webp" alt="lion" width="300"/>

---

1. 全自动方法

2. 安装插件`Markdown Image`
3. 右击markdown编辑界面 -> 点击`Paste Image`即可粘贴剪贴板中复制的图像。（或者使用默认快捷键`Shift+Alt+V`）
4. `git push`的时候把图片和markdown文件都一起提交即可

---

3. 详细事项：

1. 按快捷键后该插件会自动在项目根目录下新建一个`images`文件夹（如不存在），然后会把剪切板中的图像粘贴到该文件夹（参见下图），同时自动在markdown中创建图像代码。（**即手动方法的步骤1-3**）
   1. ![picture 1](./pic/A.png)  
2. 不论你在项目的哪一层级目录的markdown文件中，该插件都只会默认将图像保存到根目录下
3. 首次插入图像可能较慢
4. > 快捷键同样绕手，可以考虑修改为`Ctrl+Shift+I`
5. 如果需要频繁修改图像尺寸，推荐将`markdown-image.base.codeType`从`Markdown`设置为`HTML`格式
6. 更多设置参考官方教程：[link](https://github.com/imlinhanchao/vsc-markdown-image/blob/HEAD/README.zh-cn.md)

## 四.公式使用(参考Latex语法)
1. **行内公式**
- $f(x) = Ax +b $
- $f(x) \sim \mathcal{GP}(m(x), k(x,x'))$
2. **块内公式**
$$
A = 
\begin{vmatrix}
    a_{11} & a_{12} \\
    a_{21} & a_{22}
\end{vmatrix}
$$
- Latex符号请参考[link](https://github.com/LinXueyuanStdio/LaTeX_OCR_PRO)
- Latex教程请参考[link](https://www.runoob.com/latex/latex-tutorial.html)
- 复杂公式可借助大模型进行辅助编写
## 五. 目录

1. 下载插件`Markdown All in One`
2. `Ctrl+Shift+P` -> 输入`toc` -> 选择`Create Table of Contents`即可在相应位置创建


> 注：虽然直接通过指令`[toc]`生成，vscode可以成功渲染，但github界面无法渲染成功（**不推荐**）

---

上述针对文件内目录自动生成，对于多文件的目录，如：你想在`README.md`中列出所有文件的目录，可以自行构造，示例如下：

- [Operating System](https://github.com/haooxia/CSJourney/blob/main/os/os_essence.md)
* [Computer Networks](https://github.com/haooxia/CSJourney/blob/main/network/network_essence.md)


## 六. 导出PDF

* 基于插件`Markdown Preview Enhanced`打开预览窗口
* 在pdf上右击鼠标 -> 点击Export -> Chrome(Puppetter) -> PDF
* 打印的pdf会存在当前目录
## 七.提交到Github

```shell
git add .
git commit -m "your commit message"
git push origin main
```

[教程]:https://www.runoob.com/markdown/md-link.html
[^1]:节日快乐