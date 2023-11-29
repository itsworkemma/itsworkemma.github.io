### Idea

I thought of this after the Local Digital Future Councils Roundtable event in London Oct 2023. One of the groups I was in got onto discussing how we share and use learning as Councils, and whether there should be another place that people could share the details of projects they have worked / are working on for others to learn from.

Waiting at the station I got thinking about how there are so many places for people to share what they are doing, organisations like Socitm and LOTI that share information so there's lots out there but people don't seem to be using it. Not that they can't be bothered, just its a lot to find what you need in a format you can use.

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
* Any difference using [GPT-4](https://platform.openai.com/docs/models/models) instead of GPT-3.5?
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

* For learning web scraping [Beautiful Soup: Build a Web Scraper With Python – Real Python](https://realpython.com/beautiful-soup-web-scraper-python/)
* [Web Scraping and PostgreSQL (billyfung.com)](https://billyfung.com/posts/2016-01-28-postgres-scraping/)
* On pgvector [PostgreSQL Extensions: Turning PostgreSQL Into a Vector Database With pgvector Timescale](https://www.timescale.com/learn/postgresql-extensions-pgvector)
* Learnt that "a chatbot that talks to your things" is officially known as [Retrieval-augmented generation](https://python.langchain.com/docs/use_cases/question_answering/)
* [BugBytes on YouTube / Blog](https://bugbytes.io/posts/retrieval-augmented-generation-with-langchain-and-pgvector/)
* Pgvector python examples [pgvector-python/examples/openai_embeddings.py at master · pgvector/pgvector-python (github.com)](https://github.com/pgvector/pgvector-python/blob/master/examples/openai_embeddings.py)
* Another tutorial I saved and highlighted so it must have helped me understand something I was stuck on! [Postgres Vector Database with pgvector + bit.io The Inner Join](https://innerjoin.bit.io/vector-similarity-search-in-postgres-with-bit-io-and-pgvector-c58ac34f408b)
* Plus of course the reference docs for [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
, [pgvector](https://github.com/pgvector/pgvector), [psycopg2](https://www.psycopg.org/docs/), [langchain](https://python.langchain.com/docs/get_started/introduction), [langchain API](https://api.python.langchain.com/en/stable/api_reference.html#), [OpenAI API](https://platform.openai.com/docs/api-reference), [Streamlit](https://docs.streamlit.io/library/get-started/main-concepts)
* And [Local Digital](https://www.localdigital.gov.uk/commitments/) where I nicked all the starting data from 
* Big up stack overflow and youtube
