# 快速开始指南 / Quick Start Guide

## 推荐使用最小版本

### 1. 编辑课程信息
编辑 `course_config_minimal.tex` 文件：

```latex
% 课程基本信息
\newcommand{\CourseTitle}{你的课程标题}
\newcommand{\CourseCode}{课程代码}
\newcommand{\CourseSemester}{学期信息}

% 教师信息
\newcommand{\CourseInstructorsList}{%
\textbf{教师1姓名}\\
机构名称\\
地址\\
\textbf{Email:} email@domain.com\\[0.5cm]
\textbf{教师2姓名}\\
机构名称\\
地址\\
\textbf{Email:} email2@domain.com
}
```

### 2. 编辑课程安排
编辑 `course_schedule.csv` 文件：

```csv
date,time,topic,readings
13.10.2025,13:00 - 14:30,第一课,"阅读材料1"
27.10.2025,13:00 - 14:30,第二课,"阅读材料2"
```

### 3. 编译文档
运行编译脚本：

```bash
./compile_minimal.sh
```

### 4. 查看结果
打开生成的 `course_syllabus_minimal.pdf` 文件。

## 包含的基本部分

✅ **Course Description** - 课程描述  
✅ **Participants** - 参与者  
✅ **Lecturer / Teacher** - 教师信息（支持双教师）  
✅ **German Course Equivalent** - 德语课程等价  
✅ **Format** - 课程格式  
✅ **Schedule** - 课程安排（从CSV自动生成）  
✅ **Additional Resources** - 附加资源  
  - Papers and Books（从BibTeX自动生成）  
  - Websites, Wikis, Docs  

## 双教师配置示例

配置文件中的双教师设置：

```latex
% 教师列表（用于课程内容部分）
\newcommand{\CourseInstructors}{%
\item Song Shuang (\href{mailto:song@gea.mpg.de}{song@gea.mpg.de})
\item Chris Carleton (\href{mailto:carleton@gea.mpg.de}{carleton@gea.mpg.de})
}

% 教师详细信息（用于封面）
\newcommand{\CourseInstructorsList}{%
\textbf{Song Shuang}\\
Max Planck Institute of Geoanthropology\\
Kahlaische Strasse 10, 07745 Jena, Germany\\
\textbf{Email:} \href{mailto:song@gea.mpg.de}{song@gea.mpg.de}\\
\textbf{Phone:} +491784979062\\[0.5cm]
\textbf{Chris Carleton}\\
Max Planck Institute of Geoanthropology\\
Kahlaische Strasse 10, 07745 Jena, Germany\\
\textbf{Email:} \href{mailto:carleton@gea.mpg.de}{carleton@gea.mpg.de}
}
```

## 故障排除

1. **编译错误**：确保所有文件都在同一目录
2. **参考文献不显示**：运行 `biber course_syllabus_minimal`
3. **图片不显示**：检查 `imgs/` 文件夹中的Logo文件
4. **CSV不显示**：确保CSV文件格式正确，列名匹配

## 需要帮助？

查看 `COURSE_SYLLABUS_README.md` 获取详细说明。
