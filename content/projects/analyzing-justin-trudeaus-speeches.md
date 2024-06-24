---
title: Analyzing Justin Trudeau's Speeches
date: 2019-08-20
tags:
  - technical
---
# The Rationale <a href="#f102" id="f102"></a>

Canada is entering the 2019 election season which has signs indicating that it will be a contentious event.

On one hand, Prime Minister Trudeau’s Liberals have pushed through several reforms over the last 4 years, from legalizing cannabis to buying out pipelines. On the other hand, the opposition’s energy in ousting the Liberals has increased significantly over the past year. Conservatives and NDP have selected new leaders and the Green Party has been gaining ground in popularity.

However, when Canadians ruminate over who to elect to the highest office of the land, there are only a few methods of analyzing if the candidate is suitable to become the Prime Minister:

* Social media: How active are the candidate’s accounts? Are they enticing?
* Debates: How well do candidates interact with other party platforms? What are the major holes in their opponents’ political strategy?
* Third-party analysis: Which policies brought forth by candidates are objectively the best?

These methods of analyzing candidates are crucial for the upkeep of Canadian democracy; they provide a method for individuals to select the best candidate who aligns with their ideals.

For the most part, these channels of analysis work well and are quite accessible. Unfortunately, there is one facet of politicians, especially incumbents, that is often skipped in favour of these more popular platforms of analysis.

Speeches. The official speeches of the Prime Minister are an excellent window into government policies and the overall sentiment of the Prime Minister. These speeches can be used to throughly understand the Prime Minister’s motivations and the policies the PM has put forth since the previous election.

As a recently-turned 18 year old, I finally have the honour of voting in the federal elections. Seeing no major tool for analyzing Prime Minister Justin Trudeau’s speeches, I was galvanized into creating my own.

# The Approach <a href="#0226" id="0226"></a>

**Web Scraping**

The Prime Minister’s Office releases all transcripts of the Prime Minister’s speeches at [https://pm.gc.ca/en/news/speeches](https://pm.gc.ca/en/news/speeches). The first challenge I had to overcome was to download all the speeches into a format that could be used for further analysis.

Enter web scraping. Web scraping scripts programmatically parses text from a certain website and renders it in a format that can be manipulated further through additional code. It was the perfect way for me to scrape all of Prime Minister’s Trudeau’s speeches.

Initially, I decided to use Selenium, which allows users to control a browser driver that can interact with Javascript. In the following sample of code, I instruct a Chrome driver to loop through all articles in a list and extract the date, title and the speech transcript through a combination of CSS selectors and XPATHS.

```python
for article in article_list:
   article.click()
   
   time.sleep(3)
   
   # Getting title
   title = article.find_element_by_xpath("//h1[@class = 'field-content']")
   print(title.text)  

   # Getting date
   date = article.find_element_by_class_name("date-display-single")
   print(date.text)

   # Getting place
   place = article.find_element_by_xpath("//div[@class = 'inline-date']")
   print(place.text)

   # Getting speech
   speech_div = browser.find_elements_by_xpath("//span[@lang = 'EN-CA']")
   
   for p in speech_div:
      print(p.text)
```

Unfortunately, I ran into a problem with Selenium. On the speech website, each transcript was hidden in an expandable HTML `div`. The above Selenium script could not handle this.

Instead, I decided to adopt an AJAX scraping approach. First, I noticed that each speech was downloaded using AJAX with a unique ID. Secondly, I discovered that this ID could be found in the teaser on the expandable div. Using the ID from the teaser, I programmatically downloaded all speeches using the requests library, parsed the text for important information using BeautifulSoup and saved all information in a MongoDB database.The following is the part of a the AJAX scraping script that uses AJAX requests to download the speech:

```python
def fetch_speech_details(speech_id: str) -> str:

    # AJAX requests link. Replaced ID with speech_id collected from teaser
    url = 'https://pm.gc.ca/eng/views/ajax?view_name=news_article&view_display_id=block&view_args={id}'
    url = url.format(id = speech_id)

    # Get the speech
    res = requests.get(url, headers=headers)
    res.raise_for_status()

    # Convert to proper form using BeautifulSoup
    data = res.json()
    html = data[1]['data']
    soup = BeautifulSoup(html, 'html.parser')

    # Select the speech content
    body = soup.select_one('.views-field-body')
    speech_text = body.get_text()

    return str(speech_text)
```

**Cleaning**

There were several steps that I undertook to clean up the scraped speeches:

* Tokenization: Tokenization refers to the practice of separating text into pieces called tokens. In this particular project, I was tokenizing the speeches into individual words, but I also could have tokenized the speech into sentences instead. Furthermore, I converted each token into lowercase to ensure uniformity. This was accomplished using the spacy library.
* ngram: An ngram refers to a sequence of $n$ items in a sample of text. In this project, I experimented with converting the above tokens into unigrams (one word), bigrams (two words) and trigrams (three words). The ngram function was available under the NLTK library.
* Lemmatization: this process removes inflected ends of the word to arrive at the base or lemma. For example, ‘studied’ and ‘studying’ have the lemma of ‘study’. By lemmatizing words, we are able to arrive at the base and decrease variation between sentences. It is also important to note that lemmatizing does not crudely chop off the ends of verbs (also known as stemming); rather, it uses grammar rules to arrive at the base word. The WordNet lemmatizer function in the NLTK library was utilized for this step.
* Stopword removal: In any language, there are extremely common words that do not impart any additional meaning to a sentence. For example, the sentence ‘Billy was eating pancakes before going to school’ can be converted to a non-stopword sentence of ‘Billy eating pancakes before going school’. Removing stopwords helps simplify computations for later models, such as bag-of-words while still retaining the meaning of a sentence. Stopword removal was performed using the NLTK library.

**Sentiment Analysis**

Sentiment analysis refers to the process of deciphering whether a given sentence is positive, negative or neutral. If sufficient labelled data were available, a Naive Bayes model could be used to predict whether a sentence has an overall positive or negative sentiment; however, the lack of labelled speech corpus for sentiments prevented this approach.

Instead, I utilized the VaderSentiment library, which graciously provides an API for automatic sentiment analysis scores. Compound scores were provided along with positive, neutral and negative scores; the compound score helps determine the overall sentiment of the passage.

Here is a sample of the code use to analyze sentiments in a speech:

```python
# Getting sentiment score of each speech
def sentiment_score(speech):
    # Initializing analyzer object
    analyzer = SentimentIntensityAnalyzer()

    # Outputting and returning speech sentiment score
    score = analyzer.polarity_scores(speech)
    print("Speech: ", speech)
    print("Score: ", score)

    return score
```

**Topic Analysis**

Topic analysis took several steps as I had to train my own model rather than utilize an API:

* Creation of a bag-of-words model: Machine learning algorithms have one common disadvantage — models can only work on vectors, or series of numbers. Of course, this is not the natural representation of text, so it is an integral task in natural language processing to convert text to feature vectors. One way of converting text to feature vectors is through a bag-of-words model. This mechanism requires a few steps. First, a corpus or dictionary has to be created; in my project, I used the whole collection of Prime Minister Trudeau’s speech tokens as a dictionary. Second, the model has to record all the different types of vocabulary in the dictionary and give each word a certain ID. Lastly, each speech has to be scored based on the list of vocabulary. Scoring each speech for this project was a relatively simple task: I simply counted the number of occurrences of each word-ID combination. Here is a simple diagram explaining the bag-of-words model creation.
* Creation of latent Dirichlet allocation (LDA) model: An LDA model is one of the most useful topic models that exists currently. Essentially, LDA determines the probability of a document belonging to a certain topic based on the probability of certain occurrences of text sequences within each topic. For example, if the words ‘environmentalism’ and ‘pipelines’ have a high probability of occurring in Topic 1 and if a document were to contain many occurrences of ‘environmentalism’ and ‘pipelines’, then the document would have a high probability of being a Topic 1 document. For a more beautiful and in-depth explanation of the workings of an LDA model, please visit [this article](https://medium.com/@lettier/how-does-lda-work-ill-explain-using-emoji-108abf40fa7d). In my project, this model was created on the bag-of-words model for all speeches.
* Predictions: With a model finally constructed, we can pipe each speech through a bag-of-words model to convert the speech into a feature vector and predict the topic using LDA. Unlike k-means, LDA gives the probability of a document belonging to a certain topic, so it is certainly more fuzzy than k-means. This means that the prediction output is a list of topics and their respective probabilities.

Lastly, all sentiments and topics were stored in a MongoDB database.

## Results and Analysis <a href="#19ad" id="19ad"></a>

As this project was my first NLP project, I experimented around with many analysis techniques. One of them was a wordcloud: it is a representation of all the words that were found in a speech with the size of each word corresponding to its frequency. From the wordclouds (unfortunately, I lost the wordclouds when I migrated my blogging setup), we see the following insights
* Emphasis on being Canadian: Of course, as the Prime Minister of Canada, the amount of references to ‘Canada’ or ‘Canadian’ is not surprising.
* Indigenous people: Given that Canada’s history of interactions with Indigenous has been wrought with tragedy and Prime Minister Trudeau’s policy of reconciliation, the frequency of Indigenous-related terms indicates that Trudeau has been focusing many of his efforts to attempt to correct the wrongs of the past.
* Time: It is interesting to note that Trudeau’s speeches indicates that his policy is focused more on ‘today’ and the past (‘years ago’) rather than the future, especially given that Trudeau campaigned on a platform of optimism for the future. His official speeches and the campaign promises may not be lining up as intended!

I also looked at the number of tokens for each speech on average. Here is a histogram of the number of tokens for all speeches (x-axis is the number of tokens, y-axis is the number of speeches). This distribution is roughly normal with an average of roughly 1750 words. With the average speed of 150 words/minute, that translates into an average speaking time of roughly 12 minutes. For most official speeches, that length would be fair, but campaign speeches would definitely be shorter at around 5–7 minutes.

I also wanted to examine the distributions of the various sentiment scores. For the most part, the speeches seem to have a tendency to have a neutral score. However, there are several more instances of having positive scores over negative scores as seen in the compound score distribution. There also seems to be a greater number of speeches with a more positive magnitude than negative magnitude.

Overall, Trudeau’s speech style mirrors his campaign promise of optimism in government.

Another aspect of sentiment that I wanted to analyze was the change of sentiment over time. I created a small line graph to examine any trends:
* For the most part, Prime Minister Trudeau’s speeches have been positive, as seen by the dominance of the green positive sentiment line compared to the red negative sentiment line.
* There is a prominent increase in negativity in Trudeau’s speeches from March to April. At this time, the Prime Minister’s Office was embroiled in the [SNC-Lavalin affair](https://en.wikipedia.org/wiki/SNC-Lavalin\_affair), which may have indirectly affected Trudeau’s speech style
* There is an increase in optimism as the election nears. This may be an indication that Trudeau is returning to his previous strategy of a positive outlook for Canada as the elections near.

The last major part of analysis were the topics in Trudeau’s speeches. From a 5-topic LDA construction, my script outputted the following topics. Topics 0–2 seem to be more inclined to an Indigenous topic, topic 3 is more related to the topic of Canadian identity and topic 4 is related to environmentalism.

The script then systematically went through each speech and noted down the probability of each speech having any of those topics. For example, the speech on the National Inquiry into Missing and Murdered Indigenous Women and Girls had a probability of 0.997 of having Topic 0, which intuitively makes sense.

Overall, the results were a big success.

# Conclusion <a href="#f959" id="f959"></a>

This was one of the most complex projects that I have undertaken and I have learned so much through it. Natural language processing and LDA were terms which I knew nothing about before this project; however, analyzing the Prime Minister’s speeches helped me expand my knowledge into this field of machine learning.

Furthermore, I learned loads of new technologies and skills, from packages like NLTK to non-relational database management via MongoDB. To be honest, these are technologies that I never would have learned if it were not for an in-depth project like this.

It is through highly complex projects like speech analysis that I was inspired to learn new technologies and skills. Also, this project was an excellent way to cement any skills that I already knew. I highly recommend project-based learning when exploring new skills.

With only a month to complete this project, prioritization forced me to abandon the following components that would have pushed this project a step further:

* Create one script to run all functions with one command
* Scrape more speeches: For some reason, my script had trouble scraping more than 10 speeches. This may be because of the ‘Show More’ button that would pull more speeches.
* Experiment more with bigrams and trigrams: I was really interested in how bigrams and trigrams would affect the accuracy of my LDA model so I will continue to experiment around with it.

Overall, this was quite a fun and challenging project which I will continue to experiment with. The source code for the project can be found [here](https://github.com/aaronabraham311/Trudeau-Speeches) if you would like to experiment with my analysis. For anyone in Canada, please vote in October!
