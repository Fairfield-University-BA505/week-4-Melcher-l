# The HealthStats Project

## Overview
This project is designed to provide Just-in-Time practice with Python, Jupyter, and GitHub. Each class period you will complete a short assignment that applies what you have learned in the classroom that week. __Do not do assignments until they are assigned. They may change at any time until they are formally assigned.__

__You are encouraged to collaborate with your peers.__ However, you are also responsible for learning the key lessons of each assignment. So, if you need help, ask for it and pay attention to the answers. If you know how to help someone (without doing the work for them), then please help them out.

# Part 1: Lists & Control Flow
## Theory: You should know ...
* How to find and use [Markdown syntax](https://guides.github.com/features/mastering-markdown) for headlines, lists, links, etc.
* Rudimentary Python syntax, data types, and flow of control

## Practice: You be able to ...
* Write and render basic Markdown text
* Step through embedded Python code snippets
* Import data from an external file
* Perform calculations using the imported data

## Instructions
1. __Take a few minutes to read about the [Waist to Hip Ratio](https://en.wikipedia.org/wiki/Waist%E2%80%93hip_ratio).__ You should understand it well enough to explain it to your parents and walk them through doing the analysis on themselves.
2. __Open the file `w2h_data.csv` and study the data in it, which is organized as a table in *comma separated value* (or CSV) format.__ A CSV file has data in rows and columns. Each line has the same columns in the same order, with each column separated from the next by a comma.  The first line has the column names. The second line has the first row of data, with the next row below it, etc. __We are going to use Jupyter to write a short report on Waist to Hip Ratios using examples from the `w2h_data.csv` file__.  
3. __Launch Jupyter from JuoyterHub and open the file `HealthStatsPart1.ipynb` from within this repository.__ All the notebook cells are already provided, with comments used to provide instructions. Try to read through the code and make sense of what each section of the notebook is about.
4. __Edit the Markdown cells with "EDIT THIS MARKDOWN CELL".__ Instructions are given in the comments.  
  a. For the first markdown cell
5. __Read through the code in each cell, looking for "FIX THIS" comments indicating where you need to correct the code.__ For each, write the correct code, first making sure you understand what is required.
6. __Check your work by comparing with your peers.__ Just take care that your classmates may have also gotten the code wrong.
7. __Study the code again,looking for gems and dogpiles.__ You will be asked about these in the discussion questions.
8. __From the `Kernel` menu, use `Restart and Run All` to test your notebook.__ Fix any obvious errors and repeat until you think it is right. Save your notebook when you are done.
9. __Commit and sync your work to GitHub.__ Ask if you need help.
10. __Discussion Questions__
  * How long did it take you to figure out how to do a bullet list in Markdown? What other formatting tricks did you try?
   It did not take terribly long to figure out how to do a bullet list in Markdown using the github formatting tools. I also tried bold, linked words, and image insertion in Markdown
   
  * Was there any code that you thought was particularly elegant? How about cryptic or buggy?
  The part of code that had to be converted to an integer was a bit confusing to figure out. And then not all of the rows had to be converted to integers. Also, trying to divide the waist row by the hip row was a bit buggy especially if these rows were not converted to integers. The order running the code blocks also affected things and made it cryptic to figure out.
  
  * What does the code `raw_lines = list(f)` in the first code cell do exactly? Where can we learn more about loading files? Why do we bother closing the file at the end of the cell?
  This code assigns the variable raw_lines to the csv list that was loaded in. Datacamp can help us learn more about loading files into python. After we have made an assignment of the data, we no longer need the particular file open so closing it can help the program run more efficiently. 
  
  * In the second code cell, why do we try to clean up the data all at once? Why not just deal with it as raw strings?
  This way is much more efficient than dealing with raw strings. The code is much more concise than what would have to be used if the data was being treated as raw strings. 
  * What is going on in the line below, also from the second code cell?  
  ```raw_rows = [r.rstrip('\n').split(',') for r in raw_lines]```
  For every element in the raw_lines list it strips out the '\n' and then splits ',' into a list. This is a one liner that cleans the data and then assigns that cleaned data to the variable raw_rows. 
  * What does this do?  
  ```for raw_row in raw_rows[1:]:```
  For every element in raw_raws beginning with the index 1...
  * In the third code cell, a list is extended by another list. What does that mean and how is that different from appending list items to the list? How could we do the same thing using `append()`?
  This means the list we had is being lengthened by adding more columns of data. Merely apppending list items will add additional elements to a 1 dimentional list. 
  * When might the calculation
  ```w2h_ratio = row[1]/row[2]``` give inaccurate results?
  When dividing by two non integer types 
  for example, the row titles cannot be divided together. 
