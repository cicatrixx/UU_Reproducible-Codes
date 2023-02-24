# UU_Reproducible-Codes
[![DOI](https://sandbox.zenodo.org/badge/605474627.svg)](https://sandbox.zenodo.org/badge/latestdoi/605474627)

My notes from UU course on best practices in writing reproducible code on 23-24 Feb 2023. The course was focused on R and Python. So I did some further searches to find relevant things for me in matlab that are tracked here.

Course info is here: https://utrechtuniversity.github.io/workshop-computational-reproducibility/docs/4-introduction.html
Slides: 
https://utrechtuniversity.github.io/workshop-computational-reproducibility/slides/slides_introduction.html#1
https://utrechtuniversity.github.io/workshop-computational-reproducibility/docs/6.1-readability.html#slides-4 
https://utrechtuniversity.github.io/workshop-computational-reproducibility/slides/slides_documentation.html#1


Course will give steps/habits that are good return on investment for writing reproducibile codes on the fly.

## Why spend time for reproducibility?
The point isnt as much to make your code error free and very efficient but to document it well so:
- it inspire more trust
- some one can use/debug/reproduce your work
- it may not be correct but it is accessible

## 4 facets of reproduciblity
- Documentation >> for accessiblity - easy to start and use
- Organization >> for making work transparent and gaining trust
- Automation >> make analysis steps documented
- Dissemination

## Research Compendium
Get a sample template repo w good file structure as follows:
```
git clone https://github.com/bvreede/good-enough-project-template.git
```
### Folder structure
Distinguish folder types, name them accordingly:
**Read-only**: data, metadata
**Human-generated**: code, paper, documentation
**Project-generated**: clean data, figures, models...
![image](https://user-images.githubusercontent.com/38658817/220858325-2beec598-ec2e-43ed-b07d-49ef462e87b8.png)

The tree structure for the folder can be created from the commandline using the `tree` command. You can specify if this is generated at the folder or even file level. Outputs can also be copied directly to a file.

Easy place to choose a license for your project: https://choosealicense.com/

### Tools for improving coding

FOR READABILITY
use consistent style in var naming and code structuring! Popular var/function [naming conventions](https://curc.readthedocs.io/en/latest/programming/coding-best-practices.html#variable-naming-conventions) are: 
- **Snakecase:** `variable_one`, `variable_two`
- **Pascalcase:** `VariableOne`,  `VariableTwo`
- **Camelcase:** `variableOne`, `variableTwo`
Use combo of comments, whitespaces and sections to segment your codes intuitively. 

There are style guides for better coding. There are **linters** that check if you adhere to style guides and give you comments on what to do (e.g. `lintr` in R and `autopep8` in python). Then there are **auto-formatters** that already improve the style (e.g. `styler` in R and `black` in python).

In matlab, there is a style guide: https://nl.mathworks.com/matlabcentral/fileexchange/45047-matlab-style-guidelines-cheat-sheet. I also found `mlint` and `checkcode`. But the standard code analyser is already giving these code improvement notices.
![image](https://user-images.githubusercontent.com/38658817/220894350-71f6c1e2-ecfd-4efe-a349-6bffbd43f32a.png).

Set reminders throughout your code for improvements you want to make using TODO/FIXME. this is an option in most programming languages. For matlab see here: https://www.mathworks.com/help/matlab/matlab_prog/add-reminders-to-files.html. This is like writing intermittent todos in latex file that you can compile into an overarching list in the end.

For comments, matlab also has a MarkUp language that can help create formatted text from code. Using markup in comments describing functions will autogenerate pretty documentation pages for matlab. 

Matlab Markup Cheatsheet: https://nl.mathworks.com/matlabcentral/answers/help/markup
Examples: https://nl.mathworks.com/help/matlab/matlab_prog/marking-up-matlab-comments-for-publishing.html#btfv_lg-1

FOR REUSABILITY
In the long run, it is better to have many small buliding blocks than one big block function!

Work on **code-refactoring**:
- Go through all script and use colors to distinguish code sections 
-- Use yellow for scripted code, purple for structured code (for-loops, functions, if/while statments etc.), and green for comments 
- Identify section that you can convert to function - add todos first, then prioritize what to do not versus what to save for later
- Refactor your code by rewriting for better readability and reusability
  
FOR ROBUSTNESS
Make your assumptions/expectations transparent by adding them explicitly. in the simplest case, assumptions can be if/while statements. for fancier implementations, use try/catch/except/finally statements

## Documentation
Write readme, comments in code, notebooks w examples, change log

Remove zombie code when sharing!

Write comments describing ***why*** the code is here instead of ***how*** the code works step by step. The code will describe how it works

Use docstrings in R for auto generate documentation

Consider writing docstrings at the start of coding, it can be useful for thinking and structuring your code too.

The extent to which you spend time using docstrings and similar auto generation of documentation should depend on how you will be sharing your code and who will be using it. Absolutely necessary if you make a full package, not as import if you wont share it actively.

### Writing readme
Readme is a landing page for your project. Avoid giving detailed description of your functions and codes here. Focus on intital needs for being able to access and use the project for the first time. Other detailed info should be in a documentation elsewhere.

Check the examples on the slide:
Some examples from projects with high quality documentation:

```
Bigger community software projects:
Python's Pandas
Scikit-learn
Tidyverse's Dplyr

Research software:
e-science center's 'McFly' tool (https://github.com/NLeSC/mcfly)
Utrecht University's: Automatic Systematic Review (https://github.com/asreview/asreview)
Utrecht University's MICE (https://github.com/amices/mice)

Templates and ideas:
https://gist.github.com/PurpleBooth/109311bb0361f32d87a2
https://github.com/matiassingers/awesome-readme
```
Check makeareadme.com
Check Git markdown cheatsheet: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
This is how you add comment within a MD doc `<!--this is a MD comment-->`

## Dependencies
Figure out what your dependencies are. In python use `conda` and declare your dependencies in environment.yml. In R, use `renv` to ID dependencies and package them in a lockfile.

A low hanging fruit in R is to `sessionInfo()` to get summary on packages and versions used in your current workspace. Save those to a md file or add it to your readme.

Matlab also seems to have some tools for dependency analysis: https://www.mathworks.com/help/matlab/matlab_prog/analyze-project-dependencies.html, but profiler is probably also already good.

# Potential workflow for archiving codes at the end of the project
1. Review code by color coding
2. Refactor code based on how much time you have
3. Add documentation to each script
4. Clean up file structure
5. Create a git repo with the finalized project structure.
3. Create readme and develop various aspects of the readme
 + Generate file tree
 + Figure out your dependencies
+ Figure out installation and getting started steps
+ Add other parts as needed
4. Update on git repo
5. Prepare for archiving repo on zenodo
  + create tag using the naming convention vMajor.Minor.Patch
6. Add doi from zenodo into the readme

  
