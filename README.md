# Agent-Based Modeling Seminar 2025 Fall

This repository contains the LaTeX source files for the "Agent-Based Modeling for Urban and Archaeological Studies" seminar course materials, offered at the Max Planck Institute of Geoanthropology (MPI-GEA), Department of Coevolution of Landuse and Urbanisation (DLU).

## Course Information

- **Course Title**: Agent-Based Modeling for Urban and Archaeological Studies
- **Course Code**: ABM-2025
- **Semester**: Winter Semester 2025
- **Credits**: 3 ECTS
- **Format**: In-person and Virtual (DLU, Zoom)
- **Instructors**: 
  - Chris Carleton ([carleton@gea.mpg.de](mailto:carleton@gea.mpg.de))
  - Song Shuang ([song@gea.mpg.de](mailto:song@gea.mpg.de))

## Repository Structure

```
├── MPI-GEA_DLU_ABM_seminar_2025Fall.tex  # Main LaTeX document
├── course_config.tex                     # Course configuration file
├── course_schedule.csv                   # Course schedule data
├── course_bibliography.bib               # Main bibliography file
├── chapters/                             # Lecture content
│   └── lecture1.tex                      # First lecture materials
├── refer/                                # Additional references
│   └── lecture1.bib                      # Lecture-specific bibliography
├── imgs/                                 # Image assets
│   ├── MPI-GEA_logo.pdf                 # Institution logo
│   ├── bnu_logo.png                     # Partner institution logo
│   └── Song_signature.png               # Signature file
├── QUICK_START.md                        # Quick start guide
└── README.md                             # This file
```

## Quick Start

### Prerequisites

Make sure you have the following installed:
- LaTeX distribution (TeX Live, MiKTeX, or MacTeX)
- BibLaTeX with Biber backend
- Required LaTeX packages:
  - `csvsimple` - for CSV data processing
  - `biblatex` - for bibliography management
  - `booktabs` - for professional tables
  - `longtable` - for multi-page tables
  - `geometry` - for page layout
  - `hyperref` - for hyperlinks
  - Other standard packages (see main `.tex` file)

### Compilation

To compile the course syllabus PDF:

```bash
# Compile with pdflatex
pdflatex MPI-GEA_DLU_ABM_seminar_2025Fall.tex

# Process bibliography
biber MPI-GEA_DLU_ABM_seminar_2025Fall

# Compile again to resolve references
pdflatex MPI-GEA_DLU_ABM_seminar_2025Fall.tex
pdflatex MPI-GEA_DLU_ABM_seminar_2025Fall.tex
```

Or use your LaTeX editor's build system (Overleaf, TeXShop, TeXstudio, etc.).

## Customization

### 1. Modify Course Information

Edit the `course_config.tex` file to update:
- Course title, code, and semester
- Instructor information
- Institution details
- Logo paths
- Course description

Example:
```latex
% Basic course information
\newcommand{\CourseTitle}{Your Course Title}
\newcommand{\CourseCode}{COURSE-CODE}
\newcommand{\CourseSemester}{Fall 2025}
```

### 2. Update Course Schedule

Edit the `course_schedule.csv` file to modify the schedule:

```csv
date,time,topic,readings
13.10.2025,13:00 - 14:30,Introduction to ABM with case study,Reading 1
27.10.2025,13:00 - 14:30,Building NetLogo Models,Reading 2
...
```

The table automatically formats and displays in the final PDF.

### 3. Manage References

Add references to:
- `course_bibliography.bib` - Main course bibliography
- `refer/lecture1.bib` - Lecture-specific references
- Additional `.bib` files as needed (update the `\addbibresource{}` commands in main `.tex` file)

### 4. Add Lecture Content

Create new lecture files in the `chapters/` directory:
```latex
% chapters/lecture2.tex
\newpage
\sectiontitle{Lecture 2: Advanced Topics}
\subsectiontitle{Introduction}
Your content here...
```

Then include them in the main document:
```latex
\input{chapters/lecture2.tex}
```

### 5. Control Schedule Display

Adjust the number of schedule entries shown by modifying in `course_config.tex`:
```latex
\newcommand{\MaxScheduleEntries}{8}  % Show first 8 entries
```

## Document Sections

The generated syllabus includes:

1. **Title Page** - Course title, institution logo, instructor information
2. **Course Description** - Overview of the course content and objectives
3. **Participants** - Target audience
4. **Instructors** - Contact information for all instructors
5. **German Course Equivalent** - German credit system equivalence
6. **Format** - Course delivery format details
7. **Schedule** - Automatically generated from CSV file
8. **Lecture Content** - Individual lecture materials (chapters)
9. **References & Additional Resources** - Bibliography and web resources

## Multiple Instructors Support

This template supports multiple instructors. Configure them in `course_config.tex`:

```latex
% For the title page (detailed information)
\newcommand{\CourseInstructorsList}{%
\textbf{Instructor One}\\
Institution Name\\
Address\\
\textbf{Email:} email1@domain.com\\[0.5cm]
\textbf{Instructor Two}\\
Institution Name\\
Address\\
\textbf{Email:} email2@domain.com
}

% For the instructors list (brief format)
\newcommand{\CourseInstructors}{%
\item Instructor One (\href{mailto:email1@domain.com}{email1@domain.com})
\item Instructor Two (\href{mailto:email2@domain.com}{email2@domain.com})
}
```

## Additional Resources

The syllabus includes links to relevant ABM resources:
- Mesa: Agent Based Modelling in Python - https://mesa.readthedocs.io/latest/
- NetLogo - https://www.netlogo.org/
- GIS Agents - https://www.gisagents.org/

## Troubleshooting

### Bibliography not showing
Run Biber after the first pdflatex compilation:
```bash
biber MPI-GEA_DLU_ABM_seminar_2025Fall
```

### Logo not displaying
- Check that the logo file exists in the `imgs/` folder
- Verify the path in `course_config.tex` is correct
- For PDF logos, ensure your LaTeX distribution supports PDF inclusion

### CSV table not rendering
- Ensure CSV file format is correct (UTF-8 encoding)
- Check that column names match: `date,time,topic,readings`
- Verify the `csvsimple` package is installed

### Compilation errors
- Ensure all required packages are installed
- Check for syntax errors in `.tex` files
- Review the `.log` file for detailed error messages

## License

See the `LICENSE` file for license information.

## Contact

For questions about the course or this repository:
- Chris Carleton: [carleton@gea.mpg.de](mailto:carleton@gea.mpg.de)
- Song Shuang: [song@gea.mpg.de](mailto:song@gea.mpg.de)

## Contributing

If you find issues or have suggestions for improvements, please contact the instructors.

---

**Max Planck Institute of Geoanthropology**  
Department of Coevolution of Landuse and Urbanisation  
Kahlaische Strasse 10, 07745 Jena, Germany
