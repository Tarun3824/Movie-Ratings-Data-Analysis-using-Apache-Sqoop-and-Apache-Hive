🎬 Movie Ratings Data Analysis using HDFS, Apache Sqoop & Hive

📌 Overview

This project demonstrates an end-to-end big data workflow for analyzing movie ratings using the Hadoop ecosystem. The pipeline integrates HDFS, MySQL, Apache Sqoop, and Apache Hive to efficiently store, transfer, and analyze large datasets.

It showcases how modern big data tools can be combined to extract actionable insights such as top-rated movies, active users, and rating trends.

## 🚀 Workflow

1. **Dataset Collection**  
   - The dataset (`ratings.data`) is sourced from GitHub.  
   - Contains **100,000+ rows** of user ratings with fields:  
     - `user_id`, `movie_id`, `rating (1–5)`, `timestamp`.

2. **Data Storage in HDFS**  
   - Transferred into **Hadoop Distributed File System (HDFS)** for scalable and fault-tolerant storage.

3. **Relational Storage in MySQL**  
   - Data ingested into MySQL for structured relational storage and schema enforcement.

4. **Data Movement with Apache Sqoop**  
   - Sqoop used to **import/export data** between MySQL and Hive/HDFS.  
   - Supports **full imports, incremental imports, and exports** back to MySQL.

5. **Querying with Apache Hive**  
   - Hive enables **SQL-like queries** on large datasets.  
   - Queries performed:  
     - Average rating per movie  
     - Top-rated movies  
     - Most active users  
     - Movies with most ratings  
     - Trend analysis with distinct users

📊 Example Hive Queries

-- Top rated movie
SELECT movie_id, AVG(rating) AS avg_rating
FROM ratings
GROUP BY movie_id
ORDER BY avg_rating DESC
LIMIT 1;

-- Most active user
SELECT user_id, COUNT(*) AS num_ratings
FROM ratings
GROUP BY user_id
ORDER BY num_ratings DESC
LIMIT 1;

-- Movies with more than 500 ratings
SELECT movie_id, COUNT(*) AS total_ratings
FROM ratings
GROUP BY movie_id
HAVING total_ratings > 500
ORDER BY total_ratings DESC;

🏗️ Tools & Technologies

HDFS – Scalable, fault-tolerant data storage

MySQL – Relational data management

Apache Sqoop – Data transfer between RDBMS & Hadoop ecosystem

Apache Hive – SQL-like data warehouse for analytics

Hortonworks Sandbox – Testing & execution environment

🔑 Key Takeaways

Data Movement & Integration – Seamless pipeline from GitHub → HDFS → MySQL → Hive → MySQL.

Scalability – HDFS ensures fault tolerance & big data storage.

Analytics – Hive simplifies querying large datasets.

Real-world Impact – Can be extended for recommendation engines, user profiling, and content popularity analysis.

📚 References

Hadoop Ecosystem & Hive Research Papers

ACM Digital Library, IEEE Explore, ProQuest resources
