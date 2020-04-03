# Data Visualization (Global flow of knowledge via Stack Overflow)

## 1. Dataset
Stackoverflow is a question and answer site for professional and enthusiast programmers. It has become a huge community with many developers from all over the world. We want to explore this community, discover the relationship between users' country and posts (including questions and answers) and dig out the knowledge flow between regions.

The dataset we use is from [Google BigQuery Stack Overflow](https://console.cloud.google.com/marketplace/details/stack-exchange/stack-overflow) and use SQL queries to grasp desired data. The data includes:
* Users data - it contains information about users' country of residence, id, name, account created date etc.
* Questions data - it contains questions from 2016 to 2019 including questions' id, answer count, created time, score and owner user's id and etc.
* Answers data - it contains answers from 2016 to 2019 including answers' id, created time, parent (question) id, score, owner user's id and etc.

As the location of users is not always the standard countries' name, they may be just a city or some other weird characters. Before further exploration, we need to preprocess the location of the users by mapping the location to standard countries' name and deal with problems caused by the abbreviation for some countries such as 'uk' and 'usa'. After that, we need to join users data with questions data and answers data on owner user's id, mapping questions and answers to their exact location.

## 2. Problematics
For the project, we aim to show the flow of knowledge across the world. 

For many developers, Stack Overflow is the place to gain and share knowledge. In such a fast-evolving field, with new technologies coming out every day, traditional methods of knowledge transfer simply cannot catch up. Stack Overflow breaks the geographical and social barrier: As long as one has internet access, one could have equal opportunity to ask or answer questions on Stack Overflow. This new way of democratizing knowledge gave more people access to the latest information and catalyzed the development of technology. 

Moreover, Stack Overflow also provided a new opportunity to analyze the world. With many of its information being open source, we can analyze the ways people use Stack Overflow and understand where the questions are being asked, and where they are being answered. 

With these data, we hope to give the general public an insight on the "demand" and "supply" of knowledge across different countries and the potential factors affecting the level of knowledge (social-economic status, culture etc.).

## 3. Exploratory Data Analysis
In total, our data contains over 250000 user surveys over 167 countries across the world. Most of the users are between 20-30 years old working in small to medium-sized companies with 20 - 500 employees. 

We found that American and Indian users are the two largest populations in StackOverflow. Unexpectedly, the number of Chinese users ranks the fifth despite their network is limited by firewall. Unsurprisingly, due to their large user base, users from **USA and India** contribute the most questions and answers on StackOverflow. On the other hand, users from **Central Europe** tend to post more questions per account. Averaging around 2 questions per account.

In terms of quality, the posts of users in **Scandinavian and European countries like Switzerland usually** gain higher scores than other countries, which could indicate that their posts are of higher quality.


Users in **Western Europe, like Germany, Austria, and Finland, are more active in answering questions**. Generally, users in highly industrialized are more likely to use StackOverflow as a platform to **share their knowledge**.

On the other hand, we see users **in third world countries such as Bangladash, Indoenesia** tend to ask more questions than to answer questions. They are playing a role of **knowledge receivers**.

For Switzerland, it has received 5212 answers from Indians, and given out 4211 answers to American, making these two countries the largest partners in Stack Overflow Interactions.


| Country | send to swiss | receive from swiss | surplus/deficit | relative balance |
| ------- | ------------- | ------------------ | --------------- | ---------------- |
| USA     | 4775          | 4211               | -564            | -11.8%           |
| India   | 5215          | 2327               | -2888           | -55%             |
| UK      | 1997          | 1942               | -55             | -2.7%            |
| Germany | 1855          | 2119               | +264            | +14%             |


India, the holder of the second largest user community in the world is an export champion in the Stack Overflow world. It has a predominant **net export surplus** with every major partner. 

| Country | send to India | receive from India | surplus/deficit | relative balance |
| ------- | ------------- | ------------------ | --------------- | ---------------- |
| USA     | 49856         | 66928              | +17072          | +34.2%           |
| UK      | 18807         | 28957              | + 10151         | +53.9%           |
| Germany | 13490         | 28747              | + 15257         | +113%            |
| France  | 8038          | 15114              | +7076           | +88.0%            |


The tables show the activities of Stack Overflow users in the frame of a **global trading**. We believe this is a very unique and impressive idea to compare it with trading. Based on this assumption, it can served as a metric to measure a country's computer science education's development. 


## 4. Related Work

1. related work
- Each year, Stack Overflow releases an official annual developer survey [(See the latest release here) ](https://insights.stackoverflow.com/survey/2019) destinated to reflect the characteristics of its user community around the world. This survey covers various aspects of developers’ favorite technologies to their job preferences. As we can observe from the reference link, data analysis and visualization on this survey are broad but also shallow.

- In the CS 401 Applied Data Analysis 2019, one of our team members did his final project [(See the repo here](https://github.com/dinotuku/ada-2019-project-xreators) & [data story)](https://stack-overflow-as-a-social-network.github.io) on Stack Overflow data. By using more advanced data analysis skills such as matrix factorization, machine learning etc, our team retrieved some inspiring insights on the behavior of users. 

2. Originality
In this project, our team focus on a single aspect of the data: **The global knowledge flow via Stack Overflow** as stated in the problematic part. We aim to present an **interactive**, **dynamic**, **highly interpretable** and **self-explanatory** visualization on the data. This visualization should include information like **the direction&path of knowledge flow**, **width of the flow** and **possible justifications of these observations.**

3. Inspirations taken from others:
- [corona virus spread](https://informationisbeautiful.net/visualizations/covid-19-coronavirus-infographic-datapack/)
- [flight route](https://geographica.com/en/showcase/geographica-flight-routes/)
- [Sankey diagram](https://www.iea.org/sankey/)
- [map connection](https://www.data-to-viz.com/story/MapConnection.html)



We hope viewers of our project can immediately grasp this idea of global knowledge flow from our data visualization.
