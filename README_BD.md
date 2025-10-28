
### ** SQL shema**
#### Таблица `tracks` (основная информация о треках)  

| id (PK) | title  | artist_id (FK) | album_id (FK) | genre  | mood | duration | popularity | file_url | created_at |  
|---------|--------|---------------|---------------|--------|------|----------|------------|----------|------------|  
| UUID    | String | UUID          | UUID          | String | JSON | INT      | FLOAT      | String   | Timestamp  |  

#### Таблица `artists` (исполнители)  
| id (PK) | name   | country | bio | created_at |  
|---------|--------|---------|-----|------------|  
| UUID    | String | String  | TEXT | Timestamp  |  

#### Таблица `albums` (альбомы)  
| id (PK) | title  | artist_id (FK) | release_date | created_at |  
|---------|--------|---------------|--------------|------------|  
| UUID    | String | UUID          | Date         | Timestamp  |  

#### Таблица `playlists` (плейлисты)  
| id (PK) | name   | user_id (FK) | created_at |  
|---------|--------|-------------|------------|  
| UUID    | String | UUID        | Timestamp  |  

#### Таблица `playlist_tracks` (многие ко многим: плейлисты ↔ треки)  
| playlist_id (FK) | track_id (FK) | added_at |  
|------------------|--------------|----------|  
| UUID            | UUID         | Timestamp  |  

---

### ** NoSQL (MongoDB)**
```json
{
  "_id": "uuid",
  "title": "Song A",
  "artist": "Artist nickname",
  "url": "http://object_storage/location",
  "album": "album name",
  "albumArtUrl":"albumArtUrl",
  "previewUrl":  "previewUrl",
  "genre": ["Jazz"],
  "file_url": "https://cdn.example.com/music/uuid.mp3",
  "year": "2025"
}
```
