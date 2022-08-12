# Fake-News-Detection-Whatsapp-Bot

“Fake news” is a term that has come to mean different things to different people. At its core, we are defining
According to 30seconds.org:

“Fake news” is a term used to refer to fabricated news. Fake news is an invention — a lie created out of nothing — that takes the appearance of real news with the aim of deceiving people. This is what is important to remember: the information is false, but it seems true.

According to Wikipedia:

“Fake news (also known as junk news, pseudo-news, or hoax news) is a form of news consisting of deliberate disinformation or hoaxes spread via traditional news media (print and broadcast) or online social media.” The usage of the web as a medium for perceiving information is increasing daily. The amount of information loaded in social media at any point is enormous, posing a challenge to the validation of the truthfulness of the information. The main reason that drives this framework is that on an average 62% of US adults rely on social media as their main source of news. The quality of news that is being generated in social media has substantially reduced over the years. The generation of fake news is intentional by the unknown sources which are trivial, and there are existing methodologies to individually validate the users’ trustworthiness, the truthfulness of the news and user

These are four common types of fake news:

Targeted misinformation: Fictitious piece of information shared for self-serving interests. Targeted misinformation is often directed at groups that are most susceptible to receiving this type of information and easily accept and share polarizing content without verifying its authenticity.
Fake headlines: Headlines depicting fictitious facts to generate attention. These are regularly employed by less credible publications such as tabloid newspapers. Readers often quickly realize that the content of the article does not match the headline. Their titles are referred to as “clickbait headlines.”
Viral posts: There’s a plethora of new articles and content on social media networks. As a consequence, users often do not take the time to authenticate posts. Because large social networks favor shares, likes, and followers, popular posts are shown more often in a user’s threat — even if that content is fake news.
Satire: Satirical news pick up on current affairs and news items and mix them with fictitious, and often absurd events. Satire is often employed to raise awareness of social issues or criticize political wrongdoing. But there’s always the danger that humorous components go undetected and the pieces are considered to be true.
Fake news has become a huge issue in our digitally-connected world and it is no longer limited to little squabbles — fake news spreads like wildfire and is impacting millions of people every day.

How do you deal with such a sensitive issue? Countless articles are being churned out every day on the internet — how do you tell real from fake? It’s not as easy as turning to a simple fact-checker which is typically built on a story-by-story basis. As developers, can we turn to machine learning?

So in this article we will be following a more traditional supervised approach of detecting fake news by training a model on labelled data and will use Twilio WhatsApp API to infer from our model.

Requirements:
-------------

- A Twilio account ------------------> Which creates end points and also creates end user interaction pannel
- A Twilio whatsapp sandbox --------> For to customize the interface of whatsapp business clone fact checker purpose
- Python 3.10 -> Python interpreter
- Flask ----------> A python library used to run webapps that was built using python
- ngork ----------> For Hosting purpose
- Tensorflow ----> For Building,Training,Testing and deploying the models!!!!


We are using the LIAR Dataset by William Yang Wang which he used in his research paper titled "Liar, Liar
Pants on Fire": A New Benchmark Dataset for Fake News Detection.
The original dataset comes with following columns:
- Column 1: the ID of the statement ([ID].json)
- Column 2: the label
- Column 3: the statement
- Column 4: the subject(s)
- Column 5: the speaker
- Column 6: the speaker's job title
- Column 7: the state info
- Column 8: the party affiliation
- Column 9-13: the total credit history count, including the current statement
- 9: barely true counts
- 10: false counts
- 11: half true counts
- 12: mostly true counts
- 13: pants on fire counts
- Column 14: the context (venue / location of the speech or statement)
For the simplicity, we have converted it to 2 column format:
- Column 1: Statement (News headline or text)
- Column 2: Label (Label class contains: True, False)

Running the app:
----------------

1. Inside the project directory run `Run app.py`

2. Your Flask app will need to be visible from the web so Twilio can send requests to it. Ngrok lets us do this. With it installed, run the following command in your terminal in the directory your code is in. Run `ngrok http 5000` in a new terminal tab.

                           ngrok must be installed in the IDE

3. Grab that ngrok URL to configure twilio whatsapp sandbox.


And we’re good to go! Let’s test our application on WhatsApp! We can send some news headlines or facts to this sandbox and get predictions in return if everything works as expected.


