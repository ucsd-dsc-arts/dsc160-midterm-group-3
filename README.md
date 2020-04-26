# Project Title

DSC160 Data Science and the Arts - Midterm Project Repository - Spring 2020

Project Team Members: 
- Austin Le, aule@ucsd.edu
- Justin Kang, jjk139@ucsd.edu
- Sravya Voleti, srvoleti@ucsd.edu 
- Sruthi Vedantham, srvedant@ucsd.edu
- Zahra Masood, zbmasood@ucsd.edu 

## Abstract

(10 points) 

For the project proposal, please write a short abstact addressing the questions below. You should replace the entire contents of this section with one to two paragraphs addressing the following:

- What is the data set that you are going to analyze?
    - We will be analyzing image data from the wikiart website (primarily drawings, sketches, and paintings)

- What is your research question? 
    - Does art created in the same region of the world (Asia, Europe, etc) during different time periods have more variance than art created in different regions of the world during the same time period?

- What is your hypothesis about the results? 
    - We hypothesize that artwork created in the same areas of the world will have less variance than art created in different regions of the world during the same time period.

- What features of the data will you use to address your question? 
    - We will use image features that we have previously worked with in class (such as brightness, saturation, hue, and resolution). We also plan to delve deeper into image classification by using more complicated features such as calculating the Edges, image entropy, Hough lines, etc. 

- What techniques and software tools will you use to extract these features?
    - The techniques we will use will be similar to the ones we used in our first exercise. This will involve using BeautifulSoup to scrape the images from our sources as well as pandas, scipy and skimage to perform the analytical calculations once we have collected and curated our data source. These will be our base tools  and we will utilize additional resources should our scope of our project expand to account for new information we want to acquire.

- What analytic techniques will you use?
    - We plan to first calculate basic image features such as mean brightness, mean hue, image height and width, and image saturation for each of the paintings that we scrape. We will also delve deeper and analyze each painting by calculating things like Edges and and Hough lines for each painting. We also plan to look deeper into the image feature classification lecture in order to figure out more things that we plan to do. We will also be using histograms and scatter plots to compare and contrast artistic style. 

- What forms will your results take? (graphs, charts, images, sonification, Wordles, etc)
    - We are looking to implement the same tiles chart, but we may use different features of the paintings, depending on how we see fit. We will also utilize analytical charts such as pie charts, histograms, or correlation maps based on the artistic movement or time period. 

- How are you expanding on topics we have covered in class? 
    - In class we’ve discussed how to quantify artistic style. Our project expands on this by comparing artistic style across different regions of the world as well as across different time periods. 

- Why is it interesting? (personally, culturally, politically, other)
    - Culturally, this is interesting because we will be looking at the differences and similarities between people’s idea of what art is over different regions and periods of time. It will be interesting to see whether region or time-period is more influential in how artistic style changes.

## Data

(10 points) 

This section will describe your data and its origins. Each item should contain a name of the data source, a link to the source, and any necessary background information such as:
- What is your cultural data source? 
- When was it made? 
- Who created the works? 
- Is it digital native, or is it some kind of scan, recording, photo, etc., of an analog form? 

## Code

(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- data acquisition/scraping
- cleaning
- analysis
- generating results. 

Link each of your notebooks or .py files within this section, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:
- Why is this culturally relevant?
- How does your computational approach differ from the traditional art historical, musicological, manuel/subjective approach to analyzing your cultural subject? 
- How do you think the original artists/musicians would respond to this type of analysis? Would it change/inform their practice in some way?
- How do your results relate to broader social, cultural, economic political, etc., issues? 
- In what future directions could you expand this work?

## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project
- Does this code require other pip packages, software, etc?
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
