# ACM Research coding challenge (Spring 2023)

![image](https://user-images.githubusercontent.com/72369124/211179527-0ee60624-2794-4e13-bf7f-f88b5c950e44.png)

## IMPORTANT: Make sure to create a fork of this repo and share the link on your ACM Research Application Typeform submission. The coding challenge does not have to be completed at the time of you submitting the Typeform application (unless you completed the application last minute!)

Note: If it's getting down to the deadline (February 1st at 11:59 PM CST) and you don't think you will be able to finish your project on time, just complete whatever you have! Please do not work on the challenge after the deadline, but if you do need a few extra hours, make sure your challenge is done before interviews begin tomorrow (Feb 2nd).

This semester's challenge is especially open-ended. [Please refer to this dataset](https://www.kaggle.com/datasets/deepu1109/star-dataset) on Kaggle called "Star dataset to predict star types".  It contains information about 240 stars and various properties taken from "Stars and Galaxies" by Seeds and Backman. Each row contains 7 pieces of information about a star, such as its temperature, luminosity, radius, absolute magnitude, star type, star color, and spectral class.

Please note that the star type, denoted as integers, are translated as the following:
- Brown Dwarf -> Star Type = 0
- Red Dwarf -> Star Type = 1
- White Dwarf -> Star Type = 2
- Main Sequence -> Star Type = 3
- Supergiant -> Star Type = 4
- Hypergiant -> Star Type = 5

---

## INSTRUCTIONS: Please read this carefully, do not skim this!

### Here's the coding challenge: **What can you do with all of this data?** Yes, this is an **OPEN-ENDED** question and your answer should be a brief report, showcasing your skills. Can you find a pattern, answer a question, or create a visualization? In case nothing comes to mind, here are some ideas, with varying complexity:

- What is the most common star type in the data?
- What common patterns do you notice between any two properties? Ex: Is there a relationship between the star color and temperature?
- What properties are the most influential in classifying a star's type?
- Can you make a similar graph as the one shown in Kaggle to showcase the data as a Hertzsprung-Russell Diagram?
- Train a machine learning model to then predict the star type of a row of data (without the star type field) and find the model's accuracy.
Bonus: Can you find the row of data that most closely resembles our star, the Sun?

However, we strongly encourage you to come up with your own problem to solve! This is for you to showcase your skills!

You can use any programming language, framework, or library you want, but we recommend [creating a notebook in Kaggle](https://www.kaggle.com/docs/notebooks) and using Python. This will run in your browser, interlaces code with documentation, allows you to import the Stars dataset easily by pressing the "Add data" button, and gives you access to Python's high-quality, high-level libraries for working with data. [Learn more about data science in Python.](https://www.w3schools.com/datascience/ds_python.asp)

---

## How to create your solution repo **(COMPLETE STEPS #1 and #2 BEFORE YOU SUBMIT YOUR APPLICATION, AND PUT THE LINK IN THE APPLICATION)**

1. [Create a **public** fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) of this repository and name it  `ACM-Research-coding-challenge-23S` (click the "Fork" button in the top right).

2. Put the link to your fork in your ACM Research application in the question where it asks to do so. **This can just be a empty repo as you have until February 2 to work on your coding challenge in this repository**

3. Replace this README file with a description ([written in Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/about-writing-and-formatting-on-github)) of your solution. Regardless of your success, describe the problem you set out to solve and how you did it. Split it up into sections with headers, and, if relevant, include figures.

4. Make sure to include all relevant files in your fork. If you made the project in a Kaggle notebook, click **File** → **Download Notebook** to download it as an `.ipynb` file.

4. You may have to "clone" the fork you made to edit files locally on your computer and "push" them to GitHub. Learn how to do that [here](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).

5. Make sure your GitHub repo has everything important, including your report, any code you used, graphs, etc. You should not be working on this after the deadline (Feb 2).


## No collaboration policy

**You may not collaborate with anyone on this challenge.** You _are_ allowed (and encouraged) to use internet documentation. If you use existing code (either from Github, Stack Overflow, or other sources), **please cite your sources in the README**.

## Timing

Please don't spend too long on this project: **60 to 90 minutes** is reasonable. It's okay to put more time into your submission than that, but we don't expect you to get that much done; we really don't want this challenge to be a burden!

If you're *completely new* to this kind of project, however, it will likely take you more than 90 minutes. This is a *densely useful* project to go through (you will learn a lot), so we believe this is justified.

## Assessment criteria

Submissions will be evaluated holistically, in combination with the rest of your application. We will consider your effort, use of external resources, how you approached the problem, and presentation, among other considerations.

## Support and questions

Feel free to ask for clarifications in the #research-qna channel in the [ACM UTD Discord server](https://discord.gg/nJxRdKdG4d)! You can also directly    message ACM Research Co-Directors Pranav Nair or Sisi Aarukapalli-Rose on the ACM Discord server.





## Introduction

For this data set, I wanted to see how temperature played a role when compared to the star type and star color. I sought out to see if there was any relationship between a star's color and its surface temperature and if the temperature would be useful to differentiate the star types. 

## Process and Analysis

I first check all the information that Kaggle offered and noticed that it said that there was no missing data, so I knew I did not need to worry about that. I then use the `describe()` method to look at the distributions of the columns. Next I checked the colors since the `describe()` method doesn't account for non-numeric values. I notice that some color values seemed similar but were treated as different values, so I went and changed it so they wouldn't. After cleaning that up I starting graphing. Since temperature is a continuous type of data and star type is discrete, I decided to use a boxplot. I created a boxplot for each star type. Since the distributions were in different ranges I decided to make 2 sets of boxplots, one where they had the same axis range and another with different ones. For the temperature and color plot, I decided to go with a histogram since it would also be a continuous vs discrete plot. Since some colors only had few data points I decided to only choose colors that had 8 or more observations. 


The Brown and Red Dwarf Stars seem to have a similar distribution around 3000 K while the White Dwarf, Main Sequence and Supergaint Stars seem to center around 13000 K ish (But the White Dwarfs seems to have a smaller range than the other two). The Hypergiant seemed to have a grand spread in its upper limits, yet about 50% of them are around the Red and Brown Dwarf Stars.

Regarding temperature and color, Red Stars seem to have the most compact distribution around 3300 K. Blue-White and Yellow stars seem to have the largest ranges while Yellow-White and White Stars have smaller ones (mostly because of their smaller count of observations) near the lower temperatures. 


## Conclusion

Temperature alone is probably not the best indicator to determine a star's type unless you simply are looking for Red/Brown Dwarfs Stars or possibly Hypergiants. There is not enough data to determine how temperature relates to all star colors, including Yellow-White and White Stars. However, we do know that Blue/Blue-White Stars span a large range of temperatures (5000 K to 40000 K) and you can easily identify Red Stars since they mostly lie in the 3300 K area. 

