## Using NLP to build a sarcasm classifier
1.Pick two or three news sources and select a few news titles from their feed (about 5 is likely enough). For example you could select CNN, Fox News, MSNBC, NPR, PBS, Al Jazeera, RT (Russia Today), Deutsche Welle, Facebook, BBC, France24, CCTV, NHK World or another source you wish you analyze. Run your sarcasm model to predict whether the titles are interpreted as sarcastic or not. Analyze the results and comment on the different news sources you have selected.

https://www.foxnews.com/media/chad-wolf-dhs-agents-portland-riots-courthouse
https://www.cnn.com/2020/07/29/health/us-coronavirus-wednesday/index.html
https://www.npr.org/2020/07/29/896645314/irregularities-in-covid-reporting-contract-award-process-raises-new-questions
https://www.bbc.com/news/world-us-canada-53589275
https://www.nbcnews.com/politics/congress/trump-push-short-term-coronavirus-aid-fix-draws-frosty-gop-n1235230

I looked at the top stories for five well-known news sources, Fox, CNN, NPR, BBC, and NBC. I believed that because all five news sources are considered to be widely crediable, the results would be similar. However, the different top cases covered different topics, such as the Portland Protests, COVID, and Trump's response. The results showed:

Fox: [2.3196386e-02]
CNN: [5.5721387e-02]
NPR: [9.1018670e-10]
BBC: [1.3501883e-02]
NBC: [3.6340880e-10]]

Out of the five, NBC was analyzed to be least sarcastic and NPR came in second. However, all of the titles seemed to be considered not sarcastic. 

## Text generation with an RNN
1.Use the generate_text() command at the end of the exercise to produce synthetic output from your RNN model.  Run it a second time and review the output.  How has your RNN model been able to “learn” and “remember” the shakespeare text in order to reproduce a similar output?

After running the command the first time, this was the result:
"ROMEO: this will you look upon their spires,
As brain is no channels whistle Florentin
Inteigned by this intercureccosful timmn so great does death out
The rash of daint in this fest, is prepared,
From that breast, my life and part of him.

TRANIO:
Here is this tale for thanks in Parts,
Year each of my forewence, spent she stit it?
For my soul disith the hoply prince, though she fears and
slaughter here! who call the hope
That I have no attansy thing.
You art a bracl of all torches
's.'
She must do me enough.

RIVER:
I let me see our brothers and children's crown. Happy son is death,
Till therein he may time of Gloucester:
This shall disdain, so, sir:
I lo every truck to-morrow; God save your lands at maid to prepared afternoo
From my friar,
grand on A hirthy, though we swill to study.

Second Cothable, whom I,
Have cut it to live winh your daughter's queen?
As is broke of all, expecting false, I would fath you all.

CAPULET:
A dommixfer of a delight.

First Citizen:
Yes, fair lad, and his ow"

The second run returned:
"ROMEO: Open
Then grave fuiling, raventy roasies
As tcicion out o' dead, my read on thy kind of least,
Lord and woo'd hand that quaint are quit o

Al applet: but navel,
Wirthoug breart, if it put that work
I king, come by my post,
I prove it this eye and selfour mindstil to us:
Who knows false food princess at him as very preparation.
If I inmend to enforce me
To Barry from your meed, and to sister, sir; and after our neck
My prace your praises made me soft my nute,
When I have been language in Coriolix;
And brief afternoon to our proshess off.

MERCUTIO:
Old father of all,
That have tommend as you are come to eat,
Regauld the oracle: my lord, and grace a maid to say no secure?
Or I did some hating guardsing of mile,
Which I have some help frown overging: pluck aught of the name
And make comm disgract;
For such a fortively gears; I was crossly cannot abusmaid
Where I should reap a king of her: I have but levise the rest;
That runs am follows to be provoked.
I would not call them with slip and n"

The second time, the RNN model showed better results with punctuation, grammar and capitalizing letters. I am not one-hundred percent sure, but I believe the second result has better flow (follows the iambic pentameter to an extent). However, both runs have many new words and grammatical errors. Story and content wise, it is very interesting. However, I agree that the model needs to run a few more epochs for better results. 

2.Stretch goal - replace the Shakespeare text with your own selected text and run the model again.  Modify the source text as needed in order to generate_text() from the newly trained model.

## Neural machine translation with attention
1.Use the translate() command at the end of the exercise to translate three sentences from Spanish to English. How did your translations turn out? 

The three Spanish sentences were:

"Caminante, no hay camino, se hace camino al andar” — Antonio Machado -> English translation: Walker, there is no path, you make it as you walk.

'This quote comes from one of Spain’s prized poets of the Generación del ’98 (Generation of 1898). Antonio Machado’s poems are heavily influenced by his life experiences, especially the tragic event of falling madly in love with a young woman who passed away. As a result, his poetry is often dripping with despair but also an overriding love and passion for both his country and people he met along his own path. This particular quote is taken from Proverbios y Cantares (Proverbs and Cantos), in Machado’s collection “Campos de Castilla“ (“Fields of Castile”).' 

The results: just no way , go home

I had to get rid of "Caminante" (walker) because the model did not know this word. The overall result was very inaccurate in capturing the meaning/message and tone of the original quote.

![caminante](https://user-images.githubusercontent.com/67920289/88897107-c4bd2680-d218-11ea-8476-f46a022a4517.png)

"La muerte no existe, la gente solo muere cuando la olvidan; si puedes recordarme siempre estaré contigo” — Isabel Allende -> English translation: Death does not exist, people only die when they are forgotten; if you can remember me I will always be with you.

'This quote can be found in Isabel Allende’s incredible novel “Eva Luna.” Allende is considered one of Chile’s more thought-provoking and passionate contemporary writers. After both losing her daughter Paula to disease and being politically exiled, her personal life was a tough road riddled with setbacks and personal challenges which are often reflected in her works.'

The results: trust him ! 

I had to shorten the original quote to only "La muerte no existe" (death does not exist). However, the results were very off in that the model translated words like death and exist to trust and him.

![muerte](https://user-images.githubusercontent.com/67920289/88897291-09e15880-d219-11ea-9618-63857dc65181.png)

“Hay que sentir el pensamiento y pensar el sentimiento” — Miguel de Unamuno -> English translation: You must feel your thought and think your feeling.

'A fellow member of the Generación del 98, Unamuno wrote in a range of literary styles and was considered a serious intellectual during the turbulent political times of Spain in the early 20th century. He was initially a supporter of the Spanish dictator Francisco Franco, but changed his stance after witnessing bloodshed that impacted his home country. He delivered a stirring speech in front of fascist supporters denouncing their ideologies. This political context perhaps explains the above quote, which is all about carefully considering your own position and following your true inner morality wherever it may take you.'

The results: good to be to be away .

This was the first quote that the model was able to read completely! There is less style in the writing, but the vocabulary/grammar form of those words are quite advanced. I believe this may be a reason why the translation was very off. 

![hay que](https://user-images.githubusercontent.com/67920289/88897604-91c76280-d219-11ea-9e48-15633d3a7eda.png)

(https://www.fluentu.com/blog/spanish/quotes-in-spanish/)

I wanted to translate a little more literature style Spanish writing to see how the model analyzes more complex verb forms and sentence structure. The model was very off overall, but I believe with more training and with more words it can function at a similar level to GoogleTranslate. I still think it is very impressive how the model was even able to learn this much!


