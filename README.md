# 🏨 Hotel Search Assistant | Gen AI Capstone Project

## 🔍 Problem Statement and Use Case
Planning travel accommodations is time-consuming and often frustrating:

1. Users need to visit multiple hotel booking sites.
2. They must manually input dates, locations, and preferences repeatedly.
3. Comparing options across different platforms is inefficient and frustrating.
4. Natural language queries (like "Find hotels in Goa for next weekend") aren't supported by most booking sites.


## How Gen AI Solves this:

This project creates an AI-powered hotel search assistant that:

- Understands natural language - Interprets casual requests like "Find 3-star hotels in Mumbai from May 5 to May 7 for 2 adults"
- Parse the requirement (location, check-in, check-out dates etc.) to create a MMT search URL
- Visit the URL and extract top 5 hotels
- For each hotel, find pricing and more info
- Summarize and presents key hotel information (prices, ratings, amenities)


### 𝗧𝗲𝗰𝗵 𝘀𝘁𝗮𝗰𝗸:
- 𝗖𝗿𝗲𝘄𝗔𝗜 for multi-agent orchestration
- 𝗕𝗿𝗼𝘄𝘀𝗲𝗿𝗯𝗮𝘀𝗲'𝘀 headless browser tool : to simulate human browsing and gather hotels data.
- 𝗚𝗲𝗺𝗶𝗻𝗶-𝟮.𝟬-𝗳𝗹𝗮𝘀𝗵-𝗹𝗶𝘁𝗲 as the underlying LLM Model


### 🛠️ 𝙏𝙝𝙚 𝙂𝙚𝙣𝘼𝙄-𝙋𝙤𝙬𝙚𝙧𝙚𝙙 𝙎𝙤𝙡𝙪𝙩𝙞𝙤𝙣
The app is built using CrewAI, a Python framework for multi-agent collaboration. 

It primarily uses the below 3 Agents-

- 𝗣𝗿𝗼𝗺𝗽𝘁 𝗣𝗮𝗿𝘀𝗲𝗿 𝗔𝗴𝗲𝗻𝘁: Extracts structured fields (location, dates, number of guests) from the user query.
- 𝗛𝗼𝘁𝗲𝗹 𝗦𝗲𝗮𝗿𝗰𝗵 𝗔𝗴𝗲𝗻𝘁: Constructs a valid search URL on MakeMyTrip and returns it for downstream use.
- 𝗥𝗲𝘀𝘂𝗹𝘁 𝗣𝗿𝗲𝘀𝗲𝗻𝘁𝗲𝗿 𝗔𝗴𝗲𝗻𝘁: Scrapes and summarizes the hotel listings from the page into a concise, human-readable format.
