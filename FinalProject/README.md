# Musify
## Group [B]: Final Project

### What works
- Searching
- Making and editing all review types
- Making, editing, and deleting playlists
- Home page


### What doesn't work
- Proper redirection when making a new review when offline

### Pages
All pictures and text you visit from these pages are cached. Upon a chache miss, you will be redirected to the offline page.
If you update or make a review, you will also be redirected to the offline page.

- Home

You can click the home icon or musify at the top.

- Login

This is the base route. You will automatically be redirected here
- Register

You can get here from the login page.
- Profile

Hit the person icon at the top.
- Search

Click the magnifying glass icon at the top.
- Song, Album, Artist review pages

Click on any picture of an artist, album, or song on home or profile or search for them.

### Caching strategy:
We chose a network-first strategy so that when the user is online, they always get the most up to date information.
If there is a connection issue, the cache is used for everything saved from get requests. If there is a cache-miss for get requests, the offline page is shown. If a post is made, the user is presenting with an offline page. 

### Contributions:

Cameron: Worked on making the installable and offline functionality

Henry: Developed dyanmic fe besides playlists

Utkrisht: Playlist functionality and api client routes for playlists

### API Routes

Method | Route                 | Description
------ | --------------------- | ---------
`POST` | `/login`              | Receives an email and password
`POST` | `/logout`             | Removes token from current user
`POST` | `/register`           | Creates a new user account and returns the new user object
`GET`  | `/users`              | Retrieves an array of all active users in the system
`GET`  | `/users/current`      | Retrieves currently logged in user 
`GET`  | `/users/current/reviews`      | Retrieves all reviews from the current user
`GET`  | `/users/current/reviews/:reviewId`      | Retrieves one review with matching review id from the current user
`GET`  | `/users/current/reviews/mbid/:mbid`      | Retrieves one review with matching mbid id from the current user
`POST` | `/users/current/reviews`      | Creates a new current user's review and returns the review.
`PUT`  | `/users/current/reviews/:reviewId`      | Updates a user's review and returns the updated review.
`GET`  | `/users/current/reviews/artists`      | Retrieves all artist reviews from the current user
`GET`  | `/users/current/reviews/albums`      | Retrieves all album reviews from the current user
`GET`  | `/users/current/reviews/songs`      | Retrieves all song reviews from the current user
`GET`  | `/users/current/reviews/sortedArtists` | Retrieves all artist reviews with artist name and sorted by score
`GET`  | `/mbid/:mbid`      | Retrieves songs, albums, or artists by the mbid and the type in the query parameters. Example: /api/mbid/e5ef6cd9-d078-4435-b005-2f4ee6d44d61?type=album. The type can be "track", "album", or "artist"
`GET`  | `/users/current/playlists`      | Retrieves all playlists from the current user
`GET`  | `/users/current/playlists/:playlistId`      | Gets a user's playlist by playlist id
`GET`  | `/users/current/playlists/:playlistId/songs`      | Gets all the songs in a specific playlist.
`POST` | `/users/current/playlists`      | Creates a new current user's playlist and returns the playlist.
`POST` | `/users/current/playlists/:playlistId/songs`      | Adds a single song to the playlist
`PUT`  | `/users/current/playlists/:playlistId`      | Updates a user's playlist's name by playlist id and returns the updated playlist.
`DELETE`  | `/users/current/playlists/:playlistId/songs/:songId`      | Deletes a song in a playlist given by playlist id.
`DELETE`  | `/users/current/playlists/:playlistId/songs`      | Deletes all songs in a user's playlist given by playlist id.
`DELETE`  | `/users/current/playlists/:playlistId`      | Deletes a user's playlist given by playlist id.
`GET`  | `/search`   | Retrieves all songs, artists, or album with matching terms. Uses query parameters to know the type (album, track, or artist) and the query (thing being searched). Example: /api/search?type=track&query=testing
`GET`  | `/charts/songs`   | Retrieves the current most popular songs globally
`GET`  | `/users/current/recommendations`      | Gets artist and song recommendations from randomly selected liked artists and songs. Returns 10 items or less, depending on how many reviews are in the system.
`GET`  | `/offline`      | Special endpoint for offline functionality

### Pages and status

Pages | Status | Wireframe
------|--------|----------
Login |  ✅  |          
Register |  ✅ |
Profile | ✅ |       
Song    |  ✅    |
Artists  |   ✅   | 
Albums   |   ✅      | 
Home   |    ✅  |
Reviews | ✅  |
Playlists |    ✅    | 
Search | ✅ | 

### ER Diagram
![image](https://user-images.githubusercontent.com/91702651/236304365-3f81edea-aca8-4659-939a-2628d485ed4a.png)
