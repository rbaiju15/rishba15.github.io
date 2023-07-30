---
permalink: /
title: "Welcome, I'm Rishon!! Read on to find out more about this blog"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Ever since I was young, I have always been fascinated by speed. Whether it was my first bike, scooter, or skateboard, if it had wheels, I went fast in it. As I grew older, I also discovered the vast world of motorsport, a collection of various racing and driving championship series from Formula 1 to Nascar to Class B Rally. But as I started high school, I began to wonder how I could transform this passion into a real career. I had always been interested in engineering, and as I thought more and more about it, I realized I could combine my passion for speed and engineering to create the next generation of transport vehicles. This all culminated in the summer of my junior year, when I built my very own electric racing go-kart capable of reaching speeds over 30mph. Check out my projects page to learn more about it. This blog is a culmination of all my research and work, including summaries of my go-kart build, my internship at Nazar Diesel, my fun blog series about Formula 1, and many more interesting tidbits. Enjoy!!  

Displaying Projects 
======
Like many engineers, I have certain projects I want to display. To do so, this site will have integrated project portfolios. These portfolios will include detailed summaries of project work, technical research and datasheets, photos and other media, and personal insights into the daily workings of the project.

Such portfolios are very important, as they can provide deep insight into what exactly I am interested in and how I approach and tackle various problems. To learn more about engineering portfolios make sure to check out this [Indeed blog](https://www.indeed.com/career-advice/career-development/what-is-portfolio-engineering). To navigate to my portfolios, simply click the portfolio navigation button at the top of the screen and select which project you would like to view.

My Research
======
I have always been someone who is constantly looking for new information. My interests are random and varied, and often lead me down wild paths. For example, my interest in geography led me to be able to name every country and its capital, my interest in the military led me on a path of restructuring my life around discipline and accountability, my interest in politics/economics led me to writing a 4000 word research paper on Rwanda, etc. Since the main focus of this page is engineering and speed, my research regarding these topics can be found under the research tab. However, for my more whimsical interests, check out my blog posts where the endless waterfall of information in my mind that is at the same time useful and useless is collected and recorded!

Experiences
------
For me, being an engineer is all about being practical. My favorite story regarding engineering is actually an excerpt from *The Scientific Blacksmith* by Mortimer E. Cooley, the founder of the Mechanical Engineering department at the University of Michigan. In it, he describes how the first class he taught in MechE had six students in it. After showing them how to light and heat up a forging furnace, he asked the students to retrieve a piece of wrought iron from a bucket of scraps in the back of the classroom. After a few minutes, the students couldn't differentiate wrought iron from the cast iron and steel in the bucket. However, when prompted, all of them could easily explain the chemical differences between the types of iron. Cooley took this as a lesson to always focus on the practical, and how engineers could take the heaps of theoretical knowledge they had and apply that to actual engineering projects. This is the reason why I believe engineering experiences to be of the utmost importance. Even with all the research and knowledge in the world, without a practical way to apply it, it is of no use. That is why I have dedicated an entire section to the engineering experiences I have taken part in, and how those experiences have turned me into a better more insightful engineer.

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the academicpages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring academicpages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful.
