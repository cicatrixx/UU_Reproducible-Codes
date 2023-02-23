# UU_Reproducible-Codes
Notes from UU course on best practices in writing reproducible code

Course info is here:
https://utrechtuniversity.github.io/workshop-computational-reproducibility/docs/4-introduction.html


Course will give steps/habits that are good return on investment in reproducibility.

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
use consistent style in var naming and code structuring!
There are style guides for better coding. There are **linters** that check if you adhere to style guides and give you comments on what to do (e.g. `lintr` in R and `autopep8` in python). Then there are **auto-formatters** that already improve the style (e.g. `styler` in R and `black` in python).

In matlab, I found `mlint` and `checkcode`.
![image](https://user-images.githubusercontent.com/38658817/220894350-71f6c1e2-ecfd-4efe-a349-6bffbd43f32a.png)

Set reminders throughout your code for improvements you want to make using TODO/FIXME. this is an option in most programming languages. For matlab see here: https://www.mathworks.com/help/matlab/matlab_prog/add-reminders-to-files.html. This is like writing intermittent todos in latex file that you can compile into an overarching list in the end.





