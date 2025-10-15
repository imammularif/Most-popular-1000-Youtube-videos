# 🎥 Most Popular 1000 YouTube Videos Dashboard

Project ini bertujuan untuk menganalisis **1000 video YouTube paling populer di dunia** berdasarkan jumlah views, likes, dan kategori, lalu memvisualisasikannya menggunakan **Google Looker Studio**.  

Analisis ini membantu memahami pola **konten yang paling menarik dan viral di YouTube.**

## 🧩 Dataset dan Tools
**Dataset:**
- Sumber: Kaggle : https://www.kaggle.com/datasets/samithsachidanandan/most-popular-1000-youtube-videos
- Format: CSV  
- Jumlah record: 1000 video  
- Variabel utama: `Video`, `Likes`, `Dislikes`, `Views`, `Category`, `Published Year`, `Rank`

**Tools yang digunakan:**
- 🧮 Excel / Google Sheets → data cleaning & eksplorasi awal  
- 📊 Google Looker Studio → visualisasi dashboard  
- 💻 (Opsional) Python Notebook → data preprocessing  

---

## 🚀 Kesimpulan
Dashboard ini menunjukkan bagaimana **kategori musik dan entertainment** masih menjadi pendorong utama popularitas di YouTube.  
Proyek ini juga menjadi contoh penerapan **data visualization** untuk memahami tren digital dan perilaku audiens online.

---

## 🧠 Tentang Proyek Ini
Proyek ini dibuat sebagai bagian dari latihan/PR untuk memperdalam kemampuan:
- Data Cleaning  
- Data Visualization  
- Data Storytelling  
- Analytical Thinking  



link dashboard: https://lookerstudio.google.com/reporting/9cf686df-3bfb-49df-8cec-e28011b818c5

## 📈 Dashboard Preview
![Dashboard Screenshot](Screenshot%202025-10-15%20001434.png)


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
select category,
count(category) as jumlah
from youtube_videos
group by category 
order by jumlah desc;
 ```

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/2.png)

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

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/3.png)

4. 
 ```bash
select rank, video_views
from youtube_videos
order by video_views desc;
 ```

![Show table](https://github.com/imammularif/Most-popular-1000-Youtube-videos/blob/main/Chapture/4.png)


