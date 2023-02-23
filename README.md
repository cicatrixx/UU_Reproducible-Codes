# UU_Reproducible-Codes
My notes from UU course on best practices in writing reproducible code on 23-24 Feb 2023

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
### Folder structure
![image](https://user-images.githubusercontent.com/38658817/220858325-2beec598-ec2e-43ed-b07d-49ef462e87b8.png)
Distinguish folder types, name them accordingly:

**Read-only**: data, metadata
**Human-generated**: code, paper, documentation
**Project-generated**: clean data, figures, models...

Easy place to choose a license for your project: https://choosealicense.com/

## Tools for improving coding

FOR READABILITY
use consistent style in var naming and code structuring! Popular var/function [naming conventions](https://curc.readthedocs.io/en/latest/programming/coding-best-practices.html#variable-naming-conventions) are: 
- **Snakecase:** `variable_one`, `variable_two`
- **Pascalcase:** `VariableOne`,  `VariableTwo`
- **Camelcase:** `variableOne`, `variableTwo`
Use combo of comments, whitespaces and sections to segment your codes intuitively. 

There are style guides for better coding. There are **linters** that check if you adhere to style guides and give you comments on what to do (e.g. `lintr` in R and `autopep8` in python). Then there are **auto-formatters** that already improve the style (e.g. `styler` in R and `black` in python).

In matlab, there is a style guide: https://nl.mathworks.com/matlabcentral/fileexchange/45047-matlab-style-guidelines-cheat-sheet. I also found `mlint` and `checkcode`. But the standard code analyser is already giving these code improvement notices.
![image](https://user-images.githubusercontent.com/38658817/220894350-71f6c1e2-ecfd-4efe-a349-6bffbd43f32a.png)

Set reminders throughout your code for improvements you want to make using TODO/FIXME. this is an option in most programming languages. For matlab see here: https://www.mathworks.com/help/matlab/matlab_prog/add-reminders-to-files.html. This is like writing intermittent todos in latex file that you can compile into an overarching list in the end.

FOR REUSABILITY
In the long run, it is better to have many small buliding blocks than one big block function!

Work on **code-refactoring**:
- Go through all script and use colors to distinguish code sections 
-- Use yellow for scripted code, purple for structured code (for-loops, functions, if/while statments etc.), and green for comments 
- Identify section that you can convert to function - add todos first, then prioritize what to do not versus what to save for later
- Refactor your code by rewriting for better readability and reusability
  
FOR ROBUSTNESS
Make your assumptions/expectations transparent by adding them explicitly. in the simplest case, assumptions can be if/while statements. for fancier implementations, use try/catch/except/finally statements
