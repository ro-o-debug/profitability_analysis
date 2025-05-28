# Video Game Sales Analysis (Tripleten Data Science Project)

### **Introduction:**
This project explores historical video game sales data from the online store 'Ice' to identify patterns that determine game success and planning effective advertising campaigns for the upcoming year (2017, based on data up to 2016).

### **Data Source:**
The dataset used in this analysis contains information on user and expert reviews, genres, platforms (e.g., Xbox or PlayStation), historical game sales data, and ESRB ratings for each game.

### **Problem Statement:**
The primary goal is to understand what factors contribute to a game's success in the market. This involves:
* Identifying general trends in game releases and sales over time.
* Analyzing the performance and lifecycle of different gaming platforms.
* Investigating the influence of user and critic scores on sales.
* Determining the most popular and profitable game genres.
* Understanding regional differences in gaming preferences (platforms, genres, and ESRB ratings).
* Testing hypotheses about user ratings across different platforms and genres.

### **Methodology and Analysis:**

1.  **Data Initialization & Preprocessing:**
    * Initial loading and inspection of the `games.csv` dataset using `pandas`.
    * Column names were converted to lowercase for consistency.
    * Data types were adjusted: `year_of_release` was converted to integer (nullable), `user_score` was converted to float (handling 'tbd' values as NaN), and `critic_score` was converted to float.
    * Missing values in 'name' or 'genre' were removed as they are crucial for identification and classification.
    * Missing `user_score` and `critic_score` values were imputed using the median score for their respective genres to avoid extreme biases.
    * Missing `rating` values were filled using the mode of the genre, assuming similar age classifications within the same category.
    * A `total_sales` column was created by summing sales across all regions (NA, EU, JP, Other).

2.  **General Data Analysis:**
    * Examined the number of games released per year, observing a peak between 2005 and 2010, followed by a decline.
    * Identified top gaming platforms by total sales (e.g., PS2, PS4, X360, Wii, DS) and analyzed their sales distribution and lifespans. Newer consoles tend to have shorter lifecycles, while some like DS had prolonged success.
    * Considered only relevant data from 2013-2016 for future model building, focusing on recent trends.

3.  **Influence of User and Critic Scores:**
    * Visualized the relationship between user/critic scores and total sales for the popular PS4 platform using scatter plots.
    * Calculated correlation coefficients: The correlation between user scores and sales was low or negative, while critic scores showed a slightly higher but still not strong correlation with sales.
    * This suggests that while reviews might influence sales, other factors like advertising and franchise popularity are more significant.

4.  **Genre Analysis:**
    * Analyzed total sales by genre, identifying top-performing genres like Action, Sports, and Shooter.
    * Calculated average sales per game by genre, showing Shooter and Sports as highly profitable, with Role-Playing and Platform also strong, especially in Japan.

5.  **Regional Profiles:**
    * Determined top platforms and genres for North America (NA), Europe (EU), and Japan (JP).
    * **Platforms:** PS4 dominates in NA and EU, while 3DS and PSV lead in Japan, reflecting regional preferences for home vs. portable consoles.
    * **Genres:** Action, Shooter, and Sports are top in NA/EU. Role-Playing and Platform are top in Japan.
    * **ESRB Ratings:** M (Mature) and T (Teen) games lead in NA/EU, while E (Everyone) and T are more popular in Japan.
    * This difference can guide marketing and content localization.

6.  **Hypothesis Testing:**
    * **Hypothesis 1:** Compared average user ratings for Xbox One and PC platforms. The test concluded there wasn't sufficient evidence to claim a significant difference in average user ratings between Xbox One and PC.
    * **Hypothesis 2:** Compared average user ratings for Action and Sports genres. The test indicated a significant difference in average user ratings between Action and Sports genres.

### **Technologies Used:**
* `Python`
* `Pandas` (for data manipulation and analysis)
* `Matplotlib` (for data visualization)
* `SciPy` (for statistical tests)
* `Jupyter Notebook`

### **Key Findings & Recommendations:**

* **Platform Focus:** Concentrate on platforms popular in target regions (PS4 for NA/EU, 3DS/PSV for Japan).
* **Genre Strategy:** Prioritize high-demand genres (Shooter, Sports globally; RPG, Platform in Japan).
* **Marketing & Reviews:** Invest in early marketing and positive reviews, especially in competitive genres (Shooters, Sports), as visibility and initial perception influence sales.
* **Seasonal Launches:** Plan releases for strategic periods, like the last quarter (festivities), when demand increases.
* **Regional Adaptation:** Tailor decisions to each region, as genre and console preferences vary drastically (e.g., Western audiences prefer action/shooters on home consoles; Japan prefers portable, role-playing/platform games, with less affinity for M-rated titles).

### **Conclusion:**
This analysis provides data-driven recommendations for the 'Ice' online store to optimize their marketing strategies and identify promising video game projects. Continuous analysis and adaptation to market trends remain crucial for success in the dynamic gaming industry.
