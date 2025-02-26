---
title: "Guidelines for creating a good Scientific poster"
date: '2019-05-01'
output: 
  html_document: 
    theme: sandstone
    toc: yes
---

This page contains general guidelines on how to make a scientific poster. You should always check the standards and requirements for the specific conference, site or session where you will be presenting. 

Otherwise to create a tried and true standard research poster see below. 

# Quick links to content on this page
* [Templates](#templates): Templates so you don't reinvent the wheel. 
* [Content](#content): Sections within the poster
* [Aestetics](#aesthetics): Font, tables, graphics, colors, logos, 
* [Printing](#printing): Guidance, location and prices
* [Evaluation](#evaluation-criteria): grading rubric
* [Examples](#examples): Selected examples

# Templates

* Choose a [powerpoint template](http://www.posterpresentations.com/html/free_poster_templates.html). Powerpoint templates are the current standard method for creating scientific posters in any field. 
    - Trifold tabletop templates are seldom used. 
    - Common sizes are 36" x 48"
    - Choose either a three, or four column layout by following the instructions along the right sidebar. 
* Biology Student Research Symposium [[website]](https://www.csuchico.edu/biol/research/student_research_symp.shtml) - Additional templates and guidelines included. These tend to be 4'x3', so a bit longer than wide.  

## Collaboration

* If you are working with a partner on this project, you can upload your powerpoint template to Google Drive. It will keep the correct scaling and allow you to simultaneously edit the file.



# Content
The following sections of information must be included in each poster. The choice of design, boxes, columns is up to you. The direction of the story should go top to bottom, then left to right. Read in columns, not rows. 

0. Title
    - Author list should have the form _Last, MI., First, Last, MI. First_ (last name, middle initial (optional), first initial or name)
    - Affiliations can be listed many ways. Your best bet is to look at other posters presented at the same event form a prior year. For a class project, simply state your year, class and section number. 
1. Introduction
    - Probably the only part that will be in paragraph form. 
    - This is your lead-in, the part that sets the stage for your analysis. 
    - Limited background and lit review go here also. 
    - Your research hypothesis should be clearly stated here. 
2. Methods (Data collection and analysis)
    - Where did your data come from?
    - Clearly state the variables that you are using, and any major recoding done (truncation, subsetting). 
    - Describe the statistical analysis methods you used. 
    - Include a sentence about what variables were tested as moderators and/or confounders. 
3. Sample characteristics
    - This is where _Table 1_ goes, a concise univariate description of your sample. 
    - Analysis sample size, N(%) for each categorical variable, mean(sd) (or mean/median) for each continuous measurement. 
5. Results
    - No more than 2 graphs or tables for bivariate comparisons
    - One multivariate table or plot. Here are some options
        - The `coefplot()` function in the `arm` package is an excellent way of displaying the results of a MV model. 
          Save the results of a model as an object `my.model <- lm(your model here)` then call `coefplot(my.model)` 
          on that object. 
        - forestplot https://cran.r-project.org/web/packages/forestplot/vignettes/forestplot.html 
        - Want to roll your own? Check out 
          [this SO post](https://stackoverflow.com/questions/32440899/coefplot-in-r-change-ci-line-colours))
        - Stargazer can make a nice table - but you should rebuild this directly in Powerpoint. 
    - At least one coefficient, the primary explanatory variable, must be interpreted in context of the problem. 
    - You are just stating results here, not justifying, explaining or connecting any meanings. 
6. Conclusions/discussion
    - Summarize results in English sentences
    - Draw and describe the big picture conclusions. Connect the breadcrumbs discussed in the results section. 
    - Make sure every statement here is backed up with evidence shown in the results. 
7. Implications
    - Why should someone care about this research? 
    - Connect to current research. Possibly more citations here. 
8. References
    - Font size can be reduced to 8 or 6 minimum. 
9. Acknowledgements & Contact info
    - Any help you received from a person not listed as an author should be acknowledged.
    - For class projects that are not presented elsewhere, I do not need to be acknowledged. 
    - The first author should include their contact email. 
    - If you have no acknowledgements, you can stick your email address in the bottom right corner as a footer. 


# Aestetics

### Font size
* Readable from 10 feet
* This tends to be at least 20-24 pt font. If using a template, stick with their defaults. 
* If presenting an e-poster err on the side of larger font, upwards of 30
* Bullets vs. Paragraphs: Pretty field specific. 
    - Often the introduction or abstract is the same paragraph used when submitting the abstract for consideration. 
    - Walls of text tend to not be read. 
* White space: Also somewhat field specific. You want the poster to be readable and eye catching. 


### Tables
* Build them in PowerPoint tables directly
* Use borders for the top, and bottom of the table
    - Use vertical borders sparingly. Probably only for the far left corner. 
    - Powerpoint has some good auto-formats you can use. 

### Graphics
* Do not copy/paste from anything, it won't scale up well. 
* Finalize the plot, then save it to your computer using the code below
    - Specify height and width in pixels. You know your monitor's aspect ratio? 800x600? 1280x800? Those are in pixels. 
    - Start with 400-600 and see what it looks like. 

```
png("C:/YOUR PATH HERE/filename.png", width=400, height=350) # open the graphics device.
plot(iris$Species) # your plot goes here
dev.off() # this closes the graphics device
```
* Always best to save the file larger rather than smaller, then manually shrink down in PPT
* You can increase the base size of text in your graphic (so it looks reasonable once you export) by adding a `base_size=` argument to your `theme()`. I would suggest starting at 18. I.e.: `theme_bw(base_size=18)`
* Want to see what it'll look like when scaled up? Follow the instructions on [[How will my poster look when it's printed?]](https://www.makesigns.com/tutorials/poster-sizing.aspx). 

### Campus Logos
Your poster is a professional publication. It should reflect your campus properly and following guidelines (where they are listed). Every campus has official logos, colors and instructions on how to correctly use these. Below I have linked the ones I could find for Chico State. 

* [[University Naming]](https://www.csuchico.edu/style-guide/visual/naming.shtml)
* [[Color Palette]](https://www.csuchico.edu/style-guide/visual/colors.shtml)
* [[Logo and Seal]](http://www.csuchico.edu/pub/graphic-standards/index.shtml)
    - This page is not fully developed yet, only the seal is available for download on this page. 
    - [[Other unofficial logos]](http://ancul.us/chico-state-logo/). Note that the use of the wildcat is not allowed unless you are discussing Athletics. Stick to using the Seal, or flame logo. 




### Colors in plots
* Colors are good - but stick to a theme/pallet. 
    - Make the colors meaningful. There's nothing informative about a rainbow. 
    - https://www.w3schools.com/colors/colors_groups.asp
    - http://paletton.com
* R Cookbook guide for colors in ggplot2: http://www.cookbook-r.com/Graphs/Colors_(ggplot2)/ 



# Printing (as appropriate)
* Don't wait until the morning of to print - this is ESPECIALLY true in Spring when there are multiple poster symposiums being conducted. 
* You can print in B&W, and any color graphics can be printed on 8x11 and taped onto the poster. 
* Don't spend a fortune!

_Prices are student reported as of Fall 2016._

* Staples ($65)
* Metagraphcs $50 36x48 --still pricey
* Ellis Art (downtown and on Esplanade) $40-50
* Kinko's B&W $10


# Evaluation Criteria
I use the following criteria to score posters. 

* **Appearance**
    - Display attracts viewer's attention.
    - Words are easy to read from an appropriate distance (3-5 feet).
    - Poster is well organized and easy to follow.
    - Graphics and other visuals enhance presentation.
    - The poster is neat and appealing to look at.
* **Content**
    - Purpose of model (question being addressed) is stated clearly.
    - I understand why someone might be interested in the model results.
    - There is enough detail about methods (e.g., creating new variables) for me to understand the model and results.
    - The sample characteristics are fully described.
    - The approach taken is appropriate for the problem and technically sound.
    - Conclusions are stated clearly.
    - Conclusions are supported by model results.
    - Limitations of the study are clear. 
* **Presentation** 
    - Presenter's response to questions demonstrated knowledge of subject matter and project
    - The presenters conducted themselves professional during the presentation.
    - It was clear that all team members understood what was being presented and had an equal contribution to the data analysis. One member did not dominate the presentation and questions.
    
    


# Examples
A selection of sample posters, class projects have comments regarding what made them stand out, and what could be improved. 


## Professional Conference Presentations

* [Patterns of Sexual Experience Among an Urban Sample of Latino and African-American 9th Grade Students](prof/2013 Jeffries APHA Sex patterns.pdf) _Jeffries, RA., De Rosa, CJ., Moulton, B., Chung, EQ._
* [Sexual Identity and Associated Factors Among and Ethnically Diverse Sample of 9th Grade Public School Students](prof/2014 Viola SRA Sexual Identity.pdf) _Viola, R., Jeffries, RA., Moulton, B., De Rosa, CJ._
* [Pre-sexual behaviors as predictors of sexual risk in adolescents: Examining alternate outcomes in sexual health education programs](prof/2017 Moulton APHA Presex proxy.pdf) _Moulton, BD., Donatello, RA., Rohrbach, L., Afifi, A., Meyer, KI., Leon, P., Lau, C._
* [Implementing a Flipped Classroom and Active Learning Techniques in General Chemistry to Augment Student Success at a Mid-Sized Rural University](prof/2017 Smith CHEM ED.pdf) _Smith, M., Aguilar, R., Cherrette, V., Rose, A., Crane, J., Park, C., Bladorn, E., Mills, H., Sherry, S., Chatha, C., Park, H., Dailey, H., Donatello, RA., Wasinger, E._
* [The Impact of Supplemental Instruction on Student Success](prof/2019 SI analysis.pdf) _Aguilar, R., Donatello, RA._



## Graduate class projects 

* [Relationship Between Alcohol Consumption and Among Gender and Age Groups](grad/2018 nesarc alcohol gender age.pdf)
    - Good tables, could use larger font. 
    - Clearly stated research questions
    - Good balance of white space. Not entirely walls of text. 
* [Species-specific tree leaf comparisons in the absence of bird predation on caterpillars](grad/2018 Caterpillars.pdf) _Parker S._
    - Excellent use of whitespace, balanced colors. Great table 1, bullet point results make it easy to read. 
* [Effects of Childhood Social Support on Trauma](grad/2016 Social support and childhood trauma.pdf) _Hostler, M., Thornton A., Wong R._
    - Clearly laid out variables of interest and RQ's. Good use of pie charts. The 3D scatterplot is not helpful. Model results presented in a nice table, but not explained. 
* [Using 2010 U.S. Census Demographics to Determine a Predictor for Beer and Wine Consumption](grad/2016 Census Alcohol.pdf) _Ellis, C., Esposito, C., LaGrange, A._
    - Great use of maps, model comparison table in the bottom middle. Bullet points clear and easy to read. Univariate summary statistics very clearly laid out. 



## Undergraduate class Projects

* [The Associations Between Familial Relationships, Daily Activities and Delinquency in Adolescents](ug/PDS Guetta.tif) _Guetta, R._
    - Very clearly laid out RQ's and introduction. Discussion connects to current literature. 
* [The Effects of Voter Demographics on the 2016 Primary Elections](ug/2016 Primary Election.pdf) _Jordan, A., Arriaza, L., Ejaz, N., Loeblich, A., Wain, C._ 
    - Watermarks on bottom corners make words difficult to read. Table under results not made in Excel. Not easy to follow direction of story 
* [Influence of drivers race on the outcome of a traffic stop](ug/2019 race traffic.pdf)
* [Investigating the association between parental dynamics and adolescent deviant behavior](ug/2017 addhealth parent dynamics and deviant behavior.pdf)
* [The relationship between one's self-image and feeling that they are liked by their peers](ug/2017 Addhealth self image.pdf)
* [The relationship between sleep disturbance and mental health](ug/2017 Addhealth sleep mental health.pdf)
* [The association between quality of sleep and general health](ug/2018 Addhealth Sleep general health.pdf)
* [Does tree type affect the type of caterpillars that are found in the presence of birds?](ug/2018 caterpillars.pdf)
* [Crater Depth & Diameter and their Association with Hemisphere & Ejecta Type](ug/2018 Mars.pdf)







