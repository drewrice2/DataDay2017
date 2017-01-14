# Data Day 2017 notes

### 9:50 AM - Patrick McFadin (DataStax) : Choose your own Time Series adventure 2nd Floor - Classroom 201

- Time series data, recommended stack (Kafka, Cassandra for data storage, Spark for data analysis)
- Stream, store
- Data expiration dates are important, why keep unnecessary / old data?
- Spark connector: open source translation layer for Spark, for the purposes of storage and analysis
- https://academy.datastax.com/resources/ds101-introduction-cassandra

### 10:40 AM - Nelson Ray (Open Door) : When A/B Testing Fails: A Case Study in Real Estate 1st Floor - Classroom 104

- A/B testing at a real estate company, residential real estate (buying and selling houses) more liquid
- Connecting residential real estate buyers to sellers
- Assuming we've identified a model *f'* that is the maximum profit for the company and quickest time to sell the house: A/B testing says we test *f* vs. *f'*
- A/B testing metrics: time to observe (days, months), so meaningful results are not known right away due to measurement lag
- Simulating offers based on past data (backtesting) allows for clarity in terms of tradeoffs between pricing models
- Results are only as good as the quality of the simulation
- Important to estimate the theoretically achievable, set goals based on that estimation
