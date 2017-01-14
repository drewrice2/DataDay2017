# Data Day 2017 notes
### 9:50 AM - Patrick McFadin (DataStax) : Choose your own Time Series adventure - 2nd Floor Classroom 201
- Time series data, recommended stack (**Kafka, Cassandra for data storage, Spark for data analysis**)
- Stream, store
- Data expiration dates are important, why keep unnecessary / old data?
- Spark connector: open source translation layer for Spark, for the purposes of storage and analysis
- https://academy.datastax.com/resources/ds101-introduction-cassandra

----
### 10:40 AM - Nelson Ray (Open Door) : When A/B Testing Fails: A Case Study in Real Estate - 1st Floor Classroom 104
- A/B testing at a real estate company, residential real estate (buying and selling houses) more liquid
- Connecting residential real estate buyers to sellers
- Assuming we've identified a model *f'* that is the maximum profit for the company and quickest time to sell the house: A/B testing says we test *f* vs. *f'*
- A/B testing metrics: time to observe (days, months), so meaningful results are not known right away due to measurement lag
- Simulating offers based on past data (backtesting) allows for clarity in terms of tradeoffs between pricing models
- Results are only as good as the quality of the simulation
- Important to estimate the theoretically achievable, set goals based on that estimation
- Increasing confidence in results has increasing costs
- Observational analysis is throwing darts at the board, simulation-based inference is the next step to testing, quasi-experiments follow in order to estimate and assure the results of the simulation make sense, and finally standard A/B testing
- Home buying: P(sell | cost)

----
### 11:30 AM - Jonathan Mugan (Deep Grammar) : How to Progress from NLP to Artificial Intelligence - 2nd Floor Classroom 203
- Computers understanding text is a long way off
- Symbolic (meaningless tokens and manual representations) vs. sub-symbolic path (word2vec, etc) to understanding text
#### Symbolic / manual representations
- **Bag-of-words** representation treats words as arbitrary symbols and looks at frequencies - vectorization
- **TFIDF** accounts for rarity of terms
- **Topic modeling**: number of topics decided ahead of time
- LDA "is a generative statistical model that allows sets of observations to be explained by unobserved groups that explain why some parts of the data are similar"
- **Sentiment analysis**: sentiment dictionary = word list with sentiment values associated with all words that might indicate sentiment
- **WordNet** organizes words into 'synsets' of things; word can be a member of multiple sets; representational sets
- **FrameNet** represents situations; frames are triggered by keywords in text (more or less)
- **ConceptNet** provides a common sense linkage between words, too shallow and haphazard to be useful
- **Semantic Web** is broad, but not deep or organized; DBpedia, categorizes text via machine learning
#### World models
- Computers need causal models of how the world works and how people interact with it
- People don't say everything to get a message across, inferences are important
- Models can be probabilistic, factor state, relational, concurrent, temporal
#### Sub-symbolic representations
- Initialize random vector
- **Word2Vec** associates words based on proximity (Italy - Rome = France - Paris)
- **Seq2seq** model encodes a sentence as a single vector; treats the task like the sentence is devoid of meaning, which is good and bad
- RNNs can answer questions, learns symbols
- In order to get a truly understanding NLP model, it needs observations from the real world

----
### 1:10 PM - Brendan Herger (Capital One) : Machine Learning with Opponents - 1st Floor Classroom 103
- Opponents = people trying to subvert a system for financial gain
- Observation weighting: uniform weights, observation age (staleness), random down-sampling (undersampling), up-sampling (oversampling), SMOTE
#### Features
- Outlier detection: train learner to recreate input vector (PCA, neural networks)
#### Modeling
- Gridsearch for tuning hyperparameters
- Nets are great at class imbalance (difficult to train, too many free parameters)
- Ensemble modeling / meta learning (tree based, linear, nets, regression)
- Genetic algorithms = score how similar a new authorization is to characteristic authorizations

----
### 2:00 PM - Alexandros Dimakis (University of Texas) : Using Graph Analytics for Machine Learning Problems - 1st Floor Classroom 103
- Graphs used for pagerank, triangle counting, profile counting, local profile counting, low rank approximation
- Machine learning problems: graph classification, vertex clustering, community detection, node classification, role identification, finding influential vertices, link prediction
#### 1. Sometimes the graph is not obvious
- 1a. "matrix completion" or recommendation systems; low rank matrix approximation; a graph can be a way to write an AL computation
- 1b. Hotel recommendations (satisfied users mean a good hotel, show 10-20 hotels with highest pagerank)
- Graphs can be formed at query time and high pagerank vertices must be discovered quickly
#### 2. Structure analytics can be used as features
- Triangle counting = # of triangles in the graph
- **Local triangle counting** on a vertex *v*: the number of triangles that *v* participates in
- Fake Facebook accounts randomly friends; real users have a higher local triangle count compared to fake users
#### 3. How to quickly and approximately perform structure analytics
- 3a. Approximate 3-profiles and 4-profiles
- "Frogwild" is pagerank counter that beats GraphLab by a significant amount

----
### 2:50 PM - Ryan Mitchell (LinkeDrive, Inc) : Web Scraping in a JavaScript World - 1st Floor Classroom 103
- Behave more like the page, not a human
- JavaScript frameworks constantly developing, makes scraping less practical
- APIs and server connections are not thought of as "data collection", but security
- Data scientist != programmer
- Selenium = Hammer, every page looks like a front end nail
- Use Selenium, wait for things to load, parse as normal
- Hidden APIs are hard to spot, easy to parse
- Ryan developed tool for identifying APIs: github.com/REMitchell/apiscraper
- Scraping is more than grabbing data from a front-end page

----
### 4:20 PM - Eric Tschetter (Remitly) : Sampling is always Bad, approximate the Good way with Sketches - 2nd Floor Classroom 201
- Tradeoffs: fidelity, size, accuracy
- Different sampling methods answer different questions
- A sampled and filtered dataset the numbers become skewed
- Summary views are great but throw out tons of data
- Summarization with approximation: saves memory, retains accuracy for the most part
- **Theta Sketches** = concert line approximation, counting "chucks" and estimating; memory for error tradeoff
- Developed by Yahoo, code on github

----
### 5:10 PM - Nikhil Buduma (Remedy Health) : Architecting a data-driven healthcare system from first principles - 2nd Floor Classroom 201
- Remedy's first product is a mobile app, physician-to-patient communication app
- Developing a human-in-the-loop ML system
- Remedy is building a comprehensive dataset for automated diagnosis and treatment
- Model distillation to transfer learning to a more interpretable model
