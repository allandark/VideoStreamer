# Video Streamer
Video streaming app where the user can play vods like tv-shows, movies.

## Technoligies
 - REST API - flask/restx
 - MySQL db
 - NginX serves frontend/reverse proxy
 - React+Typescript+Tailwind frontend
 - HLS (Http live stream)
 - NginX server holds video data
 - ffmpeg video convertions
 - Docker containers, docker compose
    - Backend /shared volume (REST)
    - Media server /shared volume (nginx)
    - Frontend (nginx)
    - Database (mysql)

## MVP
database:
- Client, admin users (one can watch, one can edit)
- Media metadata
- Genre

backend:
- crud operations
- jwt auth
- video convertion(to mp4, m8)

frontend:
- video player
- video browser
- Admin edit



### Tests

```
docker build -t media_concept .
```
```
docker run --name media_concept_container -v media:/var/media -d -p 9001:9000 media_concept
```
```
ffmpeg -i input.mp4 -c copy -f hls output.m3u8
```

```
ffmpeg -i input.mp4 \
  -codec: copy \
  -start_number 0 \
  -hls_time 10 \
  -hls_list_size 0 \
  -hls_segment_filename "/var/www/html/get/chunk/playlist%d.ts" \
  /var/www/html/get/playlist/playlist.m3u8
```

ffmpeg -i video1.mp4 -codec: copy -start_number 0 -hls_time 10 -hls_list_size 0 -hls_segment_filename "segment%d.ts" playlist.m3u8
    