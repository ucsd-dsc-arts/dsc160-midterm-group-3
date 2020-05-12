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
    - Does art created in a specific country over a period of time have more variance than art created in different countries? 

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

   Our data for our project consisted of two dataframes that contained artworks from French, Italian, British, and Russian artists. Specifically, we paid attention to portrait artworks from each of the geographical locations. Due to space constraints, the artworks were spaced out equally between the two dataframes. The primary source for our artwork was from wikiart.org and through our image scrapping capabilities, we were able to amass a portrait artworks dataset of over 6,500 pieces of portrait. A majority of our data consisted of pieces from the 19th and 20th century from a multitude of artists across the specified geographical locations. For the purposes of our analysis, artist names were omitted in the final version of the dataset. Based on the time period of our collected artworks, we can say that the artworks take on the traditional analog form of brush and paint. The art technique would allow us to perform our analytic methods consistently across both dataframes without the need to adjust for compatibility issues.

## Code

(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- data acquisition/scraping
- cleaning
- analysis
- generating results. 
['code/Image Scrapping_Statistics - Russia and French.ipynb']
Link each of your notebooks or .py files within this section, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

   Given the dataset above and our objectives in scraping these paintings from the same wiki website, we have two notebooks Image Scrapping_Statistics - Russia and French and Paintings_Scrape.ipynb that are for scraping. Since we decided upon 4 different countries we decided to divide the scraping notebooks, one for scraping British/Italian paintings and the other for Russian/French paintings. Since we chose a direct genre of “portraits” as our specific painting type, we scraped that entire webpage for artist names as well their respective countries if they resided in any of the 4. From here we entered all of the artists’ pages and got the links to their images.(Given that the amount of images we scraped were over 6000, the code may take a long while to run ~30 mins). From here we chose to get the statistics of these various paintings and add them into a dataframe. Through trial and error, we noticed that some images could not be calculated because their statistics are different(grayscale,...etc) and to mitigate this, we added try catch blocks into our code. 
Our other notebook, EDA, is where we explored the dataset itself and saw what kind of statistics they have in relation to another. Running the given code returns various histograms and groupbys that help showcase the differences between the artistic style of different countries and time periods. There is a breakdown and comparison of each country’s preference for various artistic styles, which provides the basis for what our classifier will later on use to make its classifications.
Our last notebook, “classifier code” contains our prediction modeling for paintings and where the artists originated from. We decided to use the KNN and SVM as our testing models, both of which returned similar scores in terms of prediction. In our first run of the KNN model, we used all of the following features: mean brightness, mean hue, pixels, and mean saturation. We then trained our models on these features and tested the accuracy of our predictions of region. Then, to make sure that our model needed all of these features, we selected some features rather than all of them, to see what our accuracy score would be. When we did this, we saw a significant drop in our accuracy score in predicting the region. This is why there was some repeated code after the error visualizations. Also, we ran an SVM model in order to make sure that the results from our KNN model were not because of overfitting or just because of using the wrong type of classifier. 


## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

    After running the KNN classifier using all the features (mean brightness, mean hue, pixels, and mean saturation) to predict the region, we obtained an accuracy score of 59%. This means that our classifier correctly predicted the right class a majority of the time (over 50%). To ensure that we were using the correct amount of features and that our accuracy score was optimal, we trained the model but only using 2 or 3 features. When we used only 2 and 3 features, we obtained an accuracy score of 51% and 53% respectively. Both of these are lower than when using all the features, meaning that for the classifier to accurately predict the correct region all the image features (hue, saturation, pixels, and brightness) are necessary and relevant. Because our classifier performs well while incorporating all these features, and predicts the region correctly a majority of the time, then we can say that artworks from similar regions do not have too much variance but artworks from different regions do. This is further supported by the fact that our SVM had an initial accuracy of above 50% as well. This shows that our results were not classifier dependent and that the features of paintings from each respective country contribute to its success in being classified correctly. This variance between countries and similarities within countries allowed the classifier to differentiate between distinguishing features and accurately predict which country a particular artwork is from.

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:
- Why is this culturally relevant?

    Countries in Europe are often extremely influenced by each other and this is reflected in art. When we think about art from different areas of the world, we often homogenize our thinking into “European art” or “Asian art”. By exploring this line of thought and looking into the differences between artistic style in European countries, we address a notion that is strongly held amongst the general population. 
    
- How does your computational approach differ from the traditional art historical, musicological, manual/subjective approach to analyzing your cultural subject? 

    The method we took on to analyze portrait images differs from the traditional application in the sense that it went beyond the subjective layer of the artwork. When we say subjective layer, we mean the direct subject in which the portrait is showing. Rather than discussing and analyzing the subject of the portrait, we focused around the technical aspects that were used to bring about the subject in the portrait. By focusing on features such as the mean hue, saturation and brightness, details we learned by taking this course, we were able to more broadly generalize artworks of the same kind. This negated potential issues with subjectively describing artworks that although were of the same type, were from different geographical locations and time periods.

- How do you think the original artists/musicians would respond to this type of analysis? Would it change/inform their practice in some way?

    We believe that the artists we used in our dataset would not be surprised by the results of our analysis. This would be because oftentimes, artists from the same regions learn, teach, and work with each other in order to produce their artwork. As a result, it must be common to see that different artists have very similar style choices. We believe that the results from our analysis would show artists who thought they were more unique and original, that their artwork is more similar to others in their region than they previously thought. This realization might make these artists make a more conscious shift in their artistic styles. 

- How do your results relate to broader social, cultural, economic political, etc., issues? 

    Given that we selected these paintings from different countries, we tried to specify our data and “reduce noise” by selecting only portraits. Looking at our data analysis on what kind of hues,saturations, and brightness of the images, we can see that these vary greatly between the given countries. Although this could be induced through stylistic differences, we believe that the resources as well as appreciation for art were different in these countries. In addition to the fact that these are portrait images, artists were able to present meaning through either darker or lighter elements to reflect their stance for political conflict. 

- In what future directions could you expand this work?

    To further expand this work, we can incorporate other variables into our hypothesis such as time periods or painting style to see if there is variance amongst paintings in the same country when we take time period or style into account in addition to genre. This would be interesting to examine during periods such as the Renaissance where we can use these insights to determine if artists from the same region during this time adopted similar techniques, and if the artistic styles were limited to certain regions or widespread. We can also examine and analyze other features in the art such as edge lines, hough lines, or image entropies to see how incorporating these elements would impact the classifier.

## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

- Austin Le: Worked on scraping the images from British and Italian portrait artist, cleaning the dataframe, and the final report
- Justin Kang: Worked on scraping the images from Russian and French portrait artist, cleaning the dataframe, and the final report
- Sravya Voleti: Worked on the KNN classifier, and the final report
- Sruthi Vedantham: Worked on the EDA, the SVM Classifier, and the final report
- Zahra Masood: Worked on the KNN classifier, and the final report


## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project

For this project, we used the sklearn packages in order to run our KNN and SVM classifiers. We also used matplotlib in order to generate our histograms for our Exploratory Data Analysis. In order to scrape our images, we also had to utilize BeautifulSoup. Finally, to extract our features for our classifier, such as mean saturation, we had to use skimage. 

- Does this code require other pip packages, software, etc?

No. 

- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)

No. 

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
