# Pandoc Cover Letter Template

这个模板允许你使用Markdown编写推荐信正文，然后通过Pandoc自动生成LaTeX和PDF文件。

## 文件结构

```
├── cover_letter_template.latex    # Pandoc LaTeX模板
├── cover_letter_content.md        # Markdown内容文件
├── pandoc_config.yaml            # Pandoc配置文件
├── Makefile                      # 自动化构建脚本
├── config.tex                    # LaTeX配置文件
├── data.csv                      # 审稿人数据
└── imgs/                         # 图片文件夹
```

## 使用方法

### 方法1: 使用Makefile（推荐）

```bash
# 生成PDF
make pdf

# 生成LaTeX文件
make tex

# 清理生成的文件
make clean

# 查看帮助
make help
```

### 方法2: 直接使用Pandoc命令

```bash
# 生成PDF
pandoc cover_letter_content.md \
    --template=cover_letter_template.latex \
    --pdf-engine=pdflatex \
    --output=cover_letter_output.pdf \
    --variable=MaxReviewers=5

# 生成LaTeX文件
pandoc cover_letter_content.md \
    --template=cover_letter_template.latex \
    --output=cover_letter_output.tex \
    --variable=MaxReviewers=5
```

## 自定义内容

### 1. 修改推荐信正文

编辑 `cover_letter_content.md` 文件，使用Markdown语法编写你的推荐信正文：

```markdown
# Cover Letter Content

## Abstract and Contribution

你的论文摘要和贡献...

### Key Findings

主要发现...

### Research Significance

研究意义...
```

### 2. 修改个人信息

编辑 `config.tex` 文件来修改个人信息：

```latex
% 个人信息
\newcommand{\AuthorName}{Your Name}
\newcommand{\AuthorEmail}{your.email@example.com}
% ... 其他信息
```

### 3. 修改审稿人数据

编辑 `data.csv` 文件来修改推荐的审稿人：

```csv
reviewer,email,reason
John Doe,john.doe@university.edu,Expert in water governance
Jane Smith,jane.smith@institute.edu,Climate change specialist
```

### 4. 调整显示行数

在生成时使用 `--variable=MaxReviewers=N` 参数来调整显示的审稿人数量：

```bash
pandoc cover_letter_content.md --template=cover_letter_template.latex --pdf-engine=pdflatex --output=cover_letter_output.pdf --variable=MaxReviewers=3
```

## 高级用法

### 使用变量覆盖

你可以在Pandoc命令中直接覆盖配置变量：

```bash
pandoc cover_letter_content.md \
    --template=cover_letter_template.latex \
    --pdf-engine=pdflatex \
    --output=cover_letter_output.pdf \
    --variable=AuthorName="New Name" \
    --variable=JournalName="New Journal" \
    --variable=MaxReviewers=3
```

### 批量生成

你可以创建多个Markdown文件来生成不同版本的推荐信：

```bash
# 为不同期刊生成推荐信
pandoc cover_letter_nature.md --template=cover_letter_template.latex --pdf-engine=pdflatex --output=nature_cover_letter.pdf --variable=JournalName="Nature"
pandoc cover_letter_science.md --template=cover_letter_template.latex --pdf-engine=pdflatex --output=science_cover_letter.pdf --variable=JournalName="Science"
```

## 依赖要求

- Pandoc (>= 2.0)
- LaTeX (pdflatex)
- 所有LaTeX包（moderncv, csvsimple, booktabs等）

## 故障排除

如果遇到编译错误，请检查：

1. 所有依赖包是否已安装
2. 图片文件路径是否正确
3. CSV文件格式是否正确
4. LaTeX模板语法是否正确

## 自定义模板

如果你想修改模板样式，可以编辑 `cover_letter_template.latex` 文件。模板中的 `$body$` 占位符会被Markdown内容替换。
