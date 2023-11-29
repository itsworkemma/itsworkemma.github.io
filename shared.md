### Idea

I thought of this after the Local Digital Future Councils Roundtable event in London Oct 2023. One of the groups I was in got onto discussing how we share and use learning as Councils, and whether there should be another place that people could share the details of projects they have worked / are working on for others to learn from.

Waiting at the station I got thinking about how there are so many places for people to share what they are doing, organisations like Socitm and LOTI that share information so there's lots out there but people don't seem to be using it.

Maybe the problem is in the using not the sharing...?

A chatbot type interface linked to all the shared information could enable users to ask for exactly what they want and get tailored results, without having to sift through multiple sites and PDFs.

### This thing - "Shared"

[Video here](https://youtu.be/3wNJBZtkkyI?si=HZjfdkTMI4Mmrpi5)

The snazzy music was added because I forogt to mute the screen recording! 

* To start - scraped the declaration project data and funded project data from Local Digital using BeautifulSoup
* Put it in a Postgres database using psycopg2. Added vector support with PGVector
* Used OpenAI API to generate and store vector embeddings against the data
* The main script uses Langchain and OpenAI to create an embedding for the user query, then queries the database to find related projects
* The query result is passed back to OpenAI to write the summary response, with URL links
* Used Streamlit to bung a nice interface on it

I think this is the second thing I have ever written in Python? And the first time doing any sort of database writing, web scraping, LLM meddling... so treat it as a sketch of a thought rather than the beginning of a real thing!

I find I learn things better when I work on a **Real Thing I Thought Of** rather than reading theory or working on a generic exercise. Then it sticks in my mind and helps me think of other applications for the tech.

### Other thoughts

Related to this - we talk a lot about data sharing and opening up our data which is great. But I can't help but think that as we share more and more it becomes inaccessible in another way - because of the sheer volume of data and the different places it lives in and the different formats its stored in. You need to have a fair amount of knowledge to know where to start and how to utilise what's published.

Maybe projects like this could open up that sea of data to people with a casual interest in the information behind it?

### If I do anything else with this it would be...

* Stop the greeting from popping up before every message!
* Connect to more data
  * More case studies on other sites
  * PDF business cases
* Find out why its so slow
* See if it can use [GPT-4](https://platform.openai.com/docs/models/models) instead of GPT-3.5 (cheaper) 
* Could the database structure be better? Right now its dumped in one table...
* Adjust the prompts
  * Any use extracting key terms from the question input rather than processing it as is?
  * To improve response format and consistency - right now it does whatever it wants each time
  * To write the response in a way that focuses on the area the user is asking about - now it just provides a general summary
  * Return case study date in response
* Interface - is streamlit the best option?
* Actually publish it somewhere that a real person could try it...
* Or at least get the demo code into a less embarassing state and make the repo public 

### Shoutout to some of the resources I used to make this

* ADD SOME LINKS HERE
* Big up stack overflow and youtube
