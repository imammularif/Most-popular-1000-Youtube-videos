# Most Popular 1000 YouTube Videos

## 📌 Project Overview
This repository contains a comprehensive analysis of the top 1000 most popular YouTube videos globally.  
The goal of this project is to **understand trends in video categories, engagement metrics, and global audience preferences**.

---

---

## 🛠️ Tools Used
- **Google Looker Studio** – interactive dashboard visualization  
- **CSV Dataset** – raw video data  
- Optional: Python / Jupyter Notebook for future analysis

---

## 🔍 Key Insights from Dashboard
- 🎵 **Music** category dominates ~60% of the top 1000 videos.  
- 😂 **Entertainment / Comedy** content has high engagement (likes/views balanced).  
- 🌎 Most popular videos are uploaded by **US-based channels**.  
- ⏳ Older videos (2018–2020) still dominate over newer uploads.  

> This dashboard helps visualize and explore global YouTube trends in an interactive way.

---



link dashboard: https://lookerstudio.google.com/reporting/9cf686df-3bfb-49df-8cec-e28011b818c5

## 📈 Dashboard Preview
![Dashboard Screenshot](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/visualization/looker_dashboard_screenshot.png)


## Analyze With SQL 

Tools : Dbeaver

Server : XAMPP/localhost

Tipe data yang saya gunakan :
- Rank : Serial (Primary key)
- Video : Varchar
- video_views : BigINT
- likes : BigINT
- dislikes BIGINT
- category Varchar
- published : Date


1. 
 ```bash
select SUM(video_views) as video_views,
SUM(likes) as likes,
SUM(dislikes) as dislikes,
count(`rank`) as `rank` 
from youtube_videos;
 ```

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/1.png)

2. 
 ```bash
select video,
likes,
dislikes,
video_views,
rank,
published 
from youtube_videos
order by video_views desc limit 10;
 ```

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/2.3.png)

3. 
 ```bash
 SELECT 
    category,
    COUNT(category) AS jumlah,
    ROUND(
        (COUNT(category) * 100.0 / SUM(COUNT(category)) OVER ()),
        2
    ) AS persentase
FROM youtube_videos
GROUP BY category
ORDER BY jumlah DESC;
 ```

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/Screenshot%202025-10-15%20145929.png)

4. 
 ```bash
select rank, video_views
from youtube_videos
order by video_views desc;
 ```

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/4.png)

---

## 🧾 Project Note
This repository is created as part of my **personal data analytics portfolio**.  
All datasets are used for **educational and analytical purposes only**.  
Feel free to explore or reference the project with proper credit. 🙌

---

## 👨‍💻 Author
**Imam Mularif**  
📍 Jakarta, Indonesia  
🔗 [LinkedIn](https://linkedin.com/in/imammularif) | [GitHub](https://github.com/imammularif)

---

## ⚡ Next Steps (Optional)
- Add Python notebook for exploratory data analysis (EDA)  
- Explore correlations between views, likes, and categories  
- Implement simple ML analysis for predicting video engagement



