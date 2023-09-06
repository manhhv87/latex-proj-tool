# Latex Project Managment Tool

[![Build](https://github.com/comaniac/latex-proj-tool/actions/workflows/build.yml/badge.svg)](https://github.com/comaniac/latex-proj-tool/actions/workflows/build.yml)

A toolset to traverse and manipulate a Latex project with multiple .tex files.
Here are the currently supported functionalities. You are welcome to contribute more features :)

## Project flatten

Flatten a Latex project to a single .tex file. This is useful if you want to
use latexdiff or other Latex tools that require a single .tex file.

This is mainly inspired by
this post: http://dropbearcode.blogspot.com/2011/09/multiple-file-latex-diff.html

### Usage with latexdiff

1. Install latexdiff
   - Intall Strawberry Perl from https://strawberryperl.com/ 
   - Download latexdiff from https://ctan.org/pkg/latexdiff?lang=en 
   - Unzip the latexdiff files and copy them to a C:\Strawberry\perl\bin\latexdiff folder.
2.	Install Latex Project Managment Tool
   - git clone https://github.com/manhhv87/latex-proj-tool.git 
   - pip3 install latex_proj_tool
3.	Project flatten
   - python3 -m latex_proj_tool flat old_project/main.tex --output old.tex
   - python3 -m latex_proj_tool flat new_project/main.tex --output new.tex
4.	Create diff.tex
   - cd C:\Strawberry\perl\bin\latexdiff 
   - perl latexdiff old.tex new.tex > diff.tex
5.	Upload to Overleaf and Compile diff.tex to get the PDF


## List Unused Files

List all unused files to help you clean the project.

### Usage

List all unused files in this project:
```
python3 -m latex_proj_tool find_unused my_project/main.tex
```

List all unused files in this project, excluding some files:
```
python3 -m latex_proj_tool find_unused my_project/main.tex --exclude-extensions cls,sty,bst
```

List all unused files in this project, excluding some directories:
```
python3 -m latex_proj_tool find_unused my_project/main.tex --exclude-dirs backup
```
