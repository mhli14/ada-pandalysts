---
layout: post
title: The Effect of Languages on Movies
subtitle: The Multi-Faceted Story of a Single Parameter
cover-img: "banner.jpg"
---

## Introduction: What You Speak Matters More than You Think

As of 2023, there are 7'193 spoken and written languages around the world, with only 193 UN recognised countries on the map. These languages fundementally define our ways of perceiving, thinking and communicating. Withing a language lies an entire world, and within different languages, worlds collide. Just by tracking a single language, we pull the string for a story of demographics, history, culture and if we are lucky, even bags of gold.

The movie industry is far-reaching and virtually omnipresent. It helps transmit ideas and emotions all across the globe to different peoples and cultures, maybe even helping the creation of certain values shared by all around the globe. What better place to study the impact of languages? 

Many different audiances have created strong connections with certain movies, either their local movies in their native languages, or international blockbusters released in one of the most spoken languages in the world. Many movies only have one language for a local audiance, while some reach eleven different ones (some even invented). The short yet detectable presence of a language in a movie might be a glimpse into a demographic reality of huge an acute importance. Some cultures are so affiliated with a concept or a genre that we can't think of these without them (is Paris *really* the City of Love?).

Does more languages mean more money? Which languages make more money? What are the secondary languages in big movie producing countries and does it align with known demographics? Which languages are present in a given genre, and does it align with known stereotypes, like a French Romance or a Chinese Martial Arts movie?

To answer these questions, let us take you a journey of languages in movies, in the language of data analysis!

### The Data Itself

The CMU Movie Corpus Dataset, a corpus of ~80'000 movies released between 1888 and 2016 with every detail pertaining to each movie, is our main dish. We seasoned this dish with a generous amount of Box Office Mojo Worldwide Yearly Box Office Dataset for additional **box office revenue data** and The Movies Dataset for an additional taste of **movie budget**. This body of data contains information about the length, the budget, the total revenue, the affiliated genres, the year of release and the list of languages of the movies present, many more pieces of information relating to them. 

[ Insert Relevant Distributions Describing the Dataset ]

Using this data, we will answer 4 key questions:

1. Is there a correlation between **language variety** in a movie and its **box office revenue**? 

2. The use of **which languages** are associated with a **higher box office revenue**?

3. **Which languages** a country's movies have **other than their native one**?

4. **Which languages** are more present **in a specific genre**?

We will do so with the following methods:

1. We will be performing the traditional statistical tests such as T-tests, OLS Linear Regression and Pearson's Correlation.

2. We will look for relevant covariates and perform the adequate matching to balance our dataset and therefore improve the quality of our observational study.

3. We will look for demographics and cultural ties to explain certain prevelant language trends in a given country of production.

4. We will consider and define known stereotypes to test for between genres and languages

### Dummy plot

<div>                        <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.27.0.min.js"></script>                <div id="26de9ef9-658a-463e-b915-f57517a31a6f" class="plotly-graph-div" style="height:100%; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("26de9ef9-658a-463e-b915-f57517a31a6f")) {                    Plotly.newPlot(                        "26de9ef9-658a-463e-b915-f57517a31a6f",                        [{"alignmentgroup":"True","hovertemplate":"index=%{x}\u003cbr\u003ey=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"","marker":{"color":"#636efa","pattern":{"shape":""}},"name":"","offsetgroup":"","orientation":"v","showlegend":false,"textposition":"auto","x":["Wikipedia movie ID","Freebase_movie_ID","Movie_name","Movie_release_date","Movie_box_office_revenue","Movie_runtime","Movie_languages","Movie_countries","Movie_genres","Movie_languages_clean","Movie_countries_clean","Movie_genres_clean","Movie_release_year","Movie_release_date_datetime","movie_title","movie_revenue","budget","id","release_date"],"xaxis":"x","y":[1.0,1.0,1.0,0.913885613598124,0.1242431870271989,0.7465189915342934,1.0,1.0,1.0,1.0,1.0,1.0,0.913885613598124,0.5173487367681934,0.07998039241663465,0.07998039241663465,0.11996396444138262,0.11996396444138262,0.11996396444138262],"yaxis":"y","type":"bar"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Columns"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Percentage of Non-Missing Values"},"tickformat":".0%"},"legend":{"tracegroupgap":0},"title":{"text":"Percentage of Non-Missing Values in Each Column"},"barmode":"relative"},                        {"responsive": true}                    )                };                            </script>        </div>     

## 1. Is there a correlation between the language variety in a movie and its box office revenue?

Intuitively, a movie that has more languages in it would be expected to reach a wider audiance, simply due to accessibility or increased interest. But is this really the case?

To test this, we need to assess the number of languages each movie has and test it agains the revenue the movie generates. The CMU Database provides a list of languages present in a given movie, and its box office revenue (which we enriched with the Mojo dataset). 

[insert language count distribution plot]

Yes, silent films do count as movies with no language at all, hence the 0 column. 

[insert revenue distribution plot]

### The First Look of Naiveté

We first go for a simple observation: What happens when we group the movies by the number of languages they have and gauge their revenue distribution? Can we see any linear trend? Is there a magic number of languages to opt for maximal revenue?

[insert revenue VS language count plot]

We do see a trend! The average revenue increases as the number of languages does so as well, with a dip at the 11 language mark (having that many languages in a movie is ambitious by itself though). 

We validated this result by calculating the a Peorson's correlation coefficient for the two variables, and the associated p-value: 

| Pearson's R   | P-value         | 
| :-------------: |:-------------:|
| 0.156 > 0| 9.257e-53 << 0.05|


### Looking for the Hidden Operative: Enter the Budget

The above result is naive, and maybe even too good to be true. Are there any other variables that would explain both an increasing language count AND an increasing box office revenue?

Enter the budget. One could say that a movie with a large budget would have the resources to employ mutliple languages in it, while also having the capacity to generate a lot of revenue. Can we verify the budget as a potential covariate then?

To do so we need to compare it with the language count and revenue variables

[insert budget VS revenue plot]

| Pearson's R   | P-value         | 
| :-------------: |:-------------:|
| 0.724 > 0| 1.907e-279 << 0.05|

[insert budget VS language count plot]

| Pearson's R   | P-value         | 
| :-------------: |:-------------:|
| 0.177 > 0| 1.344e-13 << 0.05|

We see in both cases that the budget correlates positively with revenue and language count, and quite significantly. As such, we have determined it to be an possible covariate

### A Wiser Analysis

Having identified the **budget** as a covariate to balance the dataset for, we also decided to do the same for the **genre** as well, given it's not-so-uniform distribution accross the dataset.

After the matching, we ran an OLS Linear Regression test, by separating the movies with more than one language as the treatment data and the rest as the control data. 

| Linear Regression Coefficient | P-value | Standard Error | 
| :-------------: |:-------------:|:-------------:|
| 1.367e+07 > 0| 0.008 << 0.05|5.13e+06|

We do get a large positive coefficient in the linear regression with a significant p-value, confirming that **a positive linear relationship between language count and box office revenue exists**. However, our Standard Error is relatively high, and therefore it would be pertinent for a future study to perform this test again with a more comprehensive dataset to further elucidate this relationship.

## 2. The Use of Which Languages are Associated with a Higher Box Office Revenue?

Maybe having multiple languages makes money indeed, but *which one* hits the jackpot?

To understand that, we will proceed in a similar fashion to our prior analysis.

### Sneak Peak: Speak in Gold (a.k.a USD)

[insert Total Revenue by Language Plot]

After enriching the revenue data with the Mojo dataset, we observe that the English language by far makes the highest cumulative value, surpassing its competitors combined: **$127,721,656,605** of revenue in total. Given the fact that the English language dominates the dataset with presence in 1322 movies (compare to Spanish in second place with 99), this is not surprising.

[insert Average Revenue per Language Plot]

When we account for that presence and instead opt to compare the average revenue earned per language, the results are drastically different.

We see that extinct or endangered languages, or the languages whose countries of origins aren't major movie producers now predimonate. Ye Old English, Croatian, Icelandic, Tibetan and Gaelic are the top five runners. 

[insert Top 5 Average Revenue Languages Plot]

A possible explanation is that these languages could feature rarely, but in big budget movies. For example: the Old English language is present in movies Beowulf and The Lord of the Rings: The Two Towers.

### Testing the Gold

We performed a linear regression with a one-hot encoding of each language in the dataset. The results are interesting:

| R-squared   | P-value         | 
| :-------------: |:-------------:|
| 0.069 | 0.0002 << 0.05|

Whereas we get a statistically significant result, the R squared being close to zero, the model doesn't necessarily well explain the variance in the data. 

Many movies had a non-significant association with the revenue, except for the following ones ordered in decreasing significance: 

| Language   | P-value         | 
| :-------------: |:-------------:|
| Old English | 0.000096|
| Croatian | 0.000503|
| Portuguese | 0.002177| 
| English | 0.003856| 
| Tibetan | 0.013901| 
| American English | 0.039020| 

We want the go further and test the 3 languages with the lowest p-values individually with matching: Old English, Croation and Portuguese.


### When the Gold Breaks Against the Stone

We performed a matching of the movie samples based on budget, genre and runtime. We imposed that the treatment condition is the presence of the language being studied. After implementing an OLS Linear Regression, we get the following:

| Language   | P-value         | 
| :-------------: |:-------------:|
| Old English | 0.377|
| Croatian | 0.938|
| Portuguese | 0.404| 

With the new p-values of our top three strongest candidates now above the significance threshold, we conclude that we cannot reject the Null Hypothesis. The data at hand **doesn't show any significant correlation between the presence of any given language and the box office revenue concretely**. 

## 3. Which Languages a Country's Movies Have Other the Native One?

Which other monsters lurk in the Loch Ness other than the one we know about? 

The presence of languages that are not the native/predominant language of country in its movies may tell us interesting stories about that country's past, present and maybe even about its future. It can tell us if demographic influences or cultural influences are predominant in their movie industry, and how they developed over time.

Here, we will explore the trends of the non-native/non-predominant languages in the movies of the top three movie producing countries in the world: The United States of America, India and the United Kingdom of Great Britain and Northern Ireland (34408, 8411 and 7868 movies produced and present in the dataset respectively).

### The Languages of Liberty

Let's take a look at the top 10 most common languages in American Movies, that are not English:

[insert American Movie Languages Plot]

Ignoring the silent films, we see that the most prevalent language after English is Spanish. Given the presence of a significant Hispanic population in the US demographics, the prevalence of Spanish here is very much expected. The immediate followers of French, German and Italian are European languages with which the US had contacts with for 200 years, and had significant levels of immigration from over the years. The others are also historically or currently relevant in American cultural sphere.

[insert Temporal Evolution of Ratios US Plot]

[insert Temporal Evolution of Spanish Ratio US Plot]

We calculated the ratio of presence of each language in American movies and the evolution of this presence across time (in 5 year intervals), between 1940 and 2015. The dominance of Spanish over the other languages is a relatively recent phenomenon, starting only around 1980-1985. Yet, it is a mostly clear path afterwards. 

Looking at the trend of the ratio of Spanish presence in American movies independently, we see an increase in 2000-2005, a trend present in other but not all languages, and is the only one to maintain that until 2010. Afterwards it suffers a downfall by 2010-2015, a trend shared by all others except for Italian. 

The evolution of the presence of Spanish follows the trends in the Hispanic demographic growth in the country. 1980-1990s seeing an increase in the Hispanic voting block, also corresponds to the start of the more dominant position of Spanish in American movies. 

### The Languages of the Ancient Subcontinent

Looking at the overall language distribution of Indian movies excluding Hindi, we see both expected and unexpected results:

[insert Indian Movie Languages Plot]

The three most prominent languages; Tamil, Malayalam and Telugu are all Southern Indian languages. These communities, while only constituting ~23% of the total Indian population, have their own movie industries (such as the Telugu Tollywood and the Tamil Kollywood) and thus are not surprisingly high up in the list. As of 2022, the combined revenue of Southern Indian film industries has surpassed that of the Mumbai-based Hindi film industry (Bollywood).

English is the fourth, as expected of it being the second official language and a lingua franca in the country, not to mention the country's colonial past. The other runner-ups of Bengali, Kannada, Urdu, Punjabi, Oriya and Marathi are all either languages present in India or its neighbours. 

[insert Temporal Evolution of Ratios India Plot]

[insert Temporal Evolution of Tamil Ratio US Plot]

The dominance of the three Southern Indian languages is uncontested since 1960s, with the others having approximately half the ratio compared to them. However, there are severe fluctuations among them. The dip of the Telugu and Tamil language ratio between 1960 and 1980 is contrasted by a huge peak in Malayalam in the same period. 

An interesting observation is that the Telugu ratio roughly follows that of Tamil until 1985, after which it resembles the Malayalam one more. English on the other hand, overtakes Telugu and becomes the 3rd most present language in the 2010-2015 band.

A close observation of the Tamil language shows a severe dip, especially in the 1970-1975 band. This trend is also present in languages such as Telugu, Bengali and Oriya. This time interval contains "The Emergency" period in India, where a state of emergency lasting for two years saw a significant repression on the press and censureship. This might explain the sudden decline in certain language ratios.

### The Languages of Fair Old Albion

The distribution of non-English languages in British movies yields a fundementally different result than that of the US or India:

[insert British Movie Languages Plot]

The dominance of European languages such as French, German, Italian and Spanish is expected, however this implies that the language trends in the UK follow cultural trends, not demographic. The second biggest demographic group in the UK is the British Asians, mostly consisted of Indians and other South/Southeastern Asians. 

Yet this fact is only visible in the presence of the Hindi language (and to a degree Mandarin), but only as the 9th. This implies that in British movies, cultural ties and history might have a bigger impact than local demographics. 

[insert Temporal Evolution of Ratios India Plot]

[insert Temporal Evolution of Tamil Ratio US Plot]

The pre-eminent position of French in the British movies is concretely established after 1970-1975, where it overtakes German for good. European languages as a whole follow a similar trend to French in their presence, with a small peak in 1980-1985 and a relatively bigger peak in 1995-2005. 

The presence of French in British movies shows a significant rise over the years, yet is challenged after 2005. French falls to a similar baseline observed between 1970 and 1995, while German and Spanish are still showing increasing trends. Italian is in significant decline after 2005. From the slow but steady growth of Japanese, Hindi and Arabic presence, we could say that the demographic impact of the British Asian minority has started to show itself in the recent times. 

## 4. Which languages are more present in a specific genre?

Is a language inherently associated with a genre, and vice versa? Can a romance movie exist in a language other than French, or can the Samurai speak a language other than Japanese?

We have created strong associations between certain cultures, languages and concepts. Might these be reflected in the presence of certain languages in a given genre? Or even better, can we ascertain new associations for genres without established stereotypes(oh dear)?

In this section, we will first observe the language distribution of each genre, then perform a t-test on a sample matched for budget, per genre group (treatment condition being the presence of the langauges of interest). Depending on data availability, we are also occasionaly removing English movies to compare the secondary languages more closely.

[insert language distribution by movie count plot]

[insert genre distribution plot]

### Martial Arts: Does Karate Speak Chinese?

[Insert Martial Arts Film Count by Language Plot]

Yes it does (Cantonese & Mandarin). In fact the sum of all classifications of Mandarin and Cantonese would double the count of English. Japanese and Korean are also represented immedately behind the Chinese dialects. English, as a singular language tag, remains on top. This does confirm the usual affiliation of East Asian languages and culture with Martial Arts movies. 

Yet this observation is not enough by itself. By conducting a t-test on the data, we see that the presence of the Chinese dialects of Cantonese, Mandarin, Japanese and Korean (all grouped jointly) is indeed significant:

| T-test value  | P-value         | 
| :-------------: |:-------------:|
| 2.977 | 0.0034 << 0.05|

This shows us concretely that **the East Asian languages are indeed significantly associated with the Martial Arts genre**.

### Samurai: Does the Katana Speak Japanese?

[Insert Samurai Film Count by Language Plot]

It sure does. In fact it is the only genre in this study where another language overtakes English with a significant margin. The importance of the "Japanese Knights" in Japan's history and cinematography is undisputed. 

While a matching on budget was not possible due to missing data, the t-test result still yields:

| T-test value  | P-value         | 
| :-------------: |:-------------:|
| 32.270 |  6.602e-227 << 0.05|

Indeed, **the Japanese Language is significantly associated with the Samurai genre**.

### War: Does the Panzer Speak German?

[Insert War Film Count by Language Plot]

Whereas we see an overwhelming dominance of the English language, we note that our language of interest, German, is the second most prominent language in the genre. It is followed closely by French and Russian, both also known for war movies to a degree. 

The usually dominant languages like Hindi and Tamil, for the general dataset, are not represent in the top ten here. This might be due to either a preference difference in India, or simply a shortcoming of the dataset. German itself is not dominant language in the dataset, hence its increased presence here is remarkable. 

The matched t-test yields:

| T-test value  | P-value         | 
| :-------------: |:-------------:|
| 3.453 |  0.0007 << 0.05|

As such, we see that **the German language is significantly associated with the War genre**.

### Romance: Does the Heart Speak French?

[Insert Romance Film Count by Language Plot]

No. 

In fact it speaks something else.

Aside from the usual English pre-eminence, we see Hindi as the second most present language in the genre. It is followed by French, Tamil (another Indian language), Spanish, Italian and German.

This is to be expected given the Bollywood's reputation for soap operas. Yet, among French and Hindi, whose association with the genre is more significant?

The matched data speaks for itself:

**French**
| T-test value  | P-value         | 
| :-------------: |:-------------:|
| 1.445 |  0.150 **>** 0.05|

**Hindi**
| T-test value  | P-value         | 
| :-------------: |:-------------:|
| 2.602 |  0.0126 << 0.05|

Indeed, the Heart Speaks Hindi more than it does French, as **the association between the genre and the French language is not significant, whereas the one for Hindi is**.

मुझे तुमसे प्यार है!

### Gangster: Does Godfather Speak Italian?

[Insert Gangster Film Count by Language Plot]

He does, Signore.

After English, Italian is the second most prevalent language in the genre. This can be explained by the prominence of the Sicilian-Italian mafia in the country's culture, but also the place of the mafia in the American (and therefore the global) cultural psyche. 

Japanese is the third runner-up, probably due to Yakuza movies present in the dataset. Either way, we want to see if there is a significant connection between the language and the genre:

| T-test value  | P-value         | 
| :-------------: |:-------------:|
| 2.046 |  0.043 < 0.05|

As such, we can argue that **there is a significant level of association between the Italian language and the Gangster Genre**.

### LGBT: What does Love Speak?

[Insert LGBT Film Count by Language Plot]

We do not have any stereotypes to test for the LGBT genre *a priori*. We see that, looking further than the usual English presence, that European languages like French, Spanish, German and Italian are mostly present in this genre. This might be due to the non or low penetreance of LGBT themes in the movie industries of non-Western socities, or due to a lack of societal acceptance in such socities. 

Hypothesis testing for the significance of the 2nd most prevalent language (French):

| T-test value  | P-value         | 
| :-------------: |:-------------:|
| -0.338 |   0.735 > 0.05|

As we can see, there is no significant association between the LGBT theme and the French language. **We currently cannot generate a concrete stereotype for this genre**.

## Conclusion: What You Speak Might be What You Are

More precisely, what you will make, what you think, how many people are there speaking the same language as you are, and what you are interested in. 

To give a summary of our results:

* Indeed, **having as many languages as possible in a movie increases the expected box office revenue** (even indepedently of the budget)! Just to be absolutely sure, maybe don't go further than 9 languages though.

* **The presence of no known, spoken, extinct or invented language in a movie is significantly associated with an increase in box office revenue**. If you are on the superstitious side, consider adopting a "Thou Shalt" speech or a trip to Zagreb though.

* **Cultural or demographic influences in a country's history can be inferred from analysing the trends of the secondary languages in its movies**. In the case of US and India, demographic or industrial trends dominate the movie language landscape, whereas in the UK, it is the cultural connections that are pre-eminent.

* **Karate speaks Chinese, the Katana speaks Japanese, the Panzer Speaks German, the Heart speaks not French but Hindi, the Godfather speaks Italian and nobody knows what the tune our hearts play.** 

There many more stories to seek out in languages in movies, but that is it from us for now. Hopefully you enjoyed this journey of language and data with us! Always remember: **ADA is the best, no matter the movie, the language or the genre!**