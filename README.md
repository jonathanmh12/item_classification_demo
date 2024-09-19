# item_classification_demo
This repo is meant to display a rough version of a classification algorithm that I designed for my current company. I replaced the actual data with a smaller publicly available set. The original use case for these models was a taxonomy containing over 2 million items and over 2500 categories. The final product included a rules engine, a la Chimera from Walmart in 2013. I was not responsible for that part and thus I have not demonstrated it here. 

# Cleaning (or lack thereof)
The data used in this demonstration is quite clean and thus did not require lemmatization, stemming, or tokenizing. This is similar to most internal item databases that I'm familiar with. 
The data I worked with in the official version consisted of medical items. These contained many abbreviations and I found that unabbreviating them proved to be useful and powerful. However the lemmatization and stemming proved counterproductive due to the fact that in the medical device industry, the suffixes and prefixes often differentiate the categories and thus were important.
# Models 
In the original case, the models required a lot more tuning than in this case with much smaller and cleaner data. Given that, I opted to tune by downscaling the data, tuning it, and then applying the parameters that were found to the models. Thus avoiding the ludicrously long training and cross validating time. 
I trained a variety of models, ultimately using a voting classifier in an effort to manage the 'corner cases' as well as possible. In practice, the voting classifier will not acheive a higher accuracy score but can handle the corner cases better to it's ability to generalize.
The predict_proba method turned out to be extremely helpful when attempting to classify into our categories and, while we are still testing it, it appears that we can identify the correct category in the top 2 for the most part, but after that it becomes unhelpful.
# Final Result
Finally, the productionalized version would likely have a UI for company employees to be able to load their excel file and retrieve recommendations without having to send a file to a person to run through the code. However, given the lack of a good option for external use, I did not include that here. Instead I'll simply say that Flask and Django are both good considerations, as well as using the Microsoft PowerBI to Azure capabilities.

Thank you!
