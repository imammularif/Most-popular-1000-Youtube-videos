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

4. 
 ```bash
select rank, video_views
from youtube_videos
order by video_views desc;
 ```

