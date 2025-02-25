---
title: How to use Extract and Rearrange in Prism to quickly format table data for ANOVAs, XY analysis, etc.
draft: false
tags:
---

> [!abstract] What's the problem?
> Transferring data from Excel to Prism can be awful in certain situations. Like when you need to transpose a bunch of vertical columns from Excel into both rows and columns in a Prism grouped sheet for 2-way ANOVA. It's super tedious and it's easy to make a mistake and copy something into the wrong place.

# The fix: Extract and Rearrange

## Setup
#### Create a multiple variables sheet in Prism

![[Pasted image 20240718113708.png]]

#### Place Excel 2-Way ANOVA data inside

Everything goes in columns with one mouse per row. Prism automatically places your categorical variables in alphabetical order. That is fine but it makes the copying a little worse so I enter my values as numbers (WT = 1, KO = 2) and drug groups as sequential numbers. This makes it an easy copy+paste job to put the values into a new sheet.

![[Pasted image 20240718121356.png]]

## Extract and Rearrange

#### Analyze Pane

Click Analyze at the top under Analysis. Under Multiple variable analysis, choose Extract and rearrange.

![[Pasted image 20240718121626.png]]

#### Choose format

Select "Grouped for two-way ANOVA" then choose the data arrangement tab. 
1. **Response variable:** your Y values, in this case `BW % Change`. 
2. **Row Factor:** Drug group. This is numerical but it doesn't have to be if you don't mind extra copy+paste steps. 
3. **Column Factor:** I'm setting this to genotype (GTNum in this case so WT and KO come out in the right order). If you just use WT and KO, you'll have to manually switch the rows after copy+paste to a new sheet.

> [!Warning] Row or Column doesn't matter
> You can set whichever groups you want to row or column. It just gives you a different shape of sheet but the analysis is the same.


![[Pasted image 20240718122041.png]]

#### Extracted values
Now you have your values. You'll find the extracted values down under the results tab on the left.

![[Pasted image 20240718122538.png]]


#### The results are even automatically graphed for you.
![[Pasted image 20240718122556.png]]
### Copy to new sheet

You can leave the results as-is if you want to but you can't edit the row titles to show your group names. For some reason you are allowed to change column titles though. I always copy to a new sheet for further analysis and graphing. 
#### Create new sheet

Create a new grouped sheet with the appropriate number of sub-columns in each group (in my case 11).

![[Pasted image 20240718122945.png]]

#### Copy your data over to the new one and edit row and column names

![[Pasted image 20240718123117.png]]

#### You're done!

![[Pasted image 20240718123350.png]]

# Congratulations, you just saved yourself a bunch of goofy copy+paste time

