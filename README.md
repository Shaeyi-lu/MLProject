# Spotify Music Recommendation Generator 

This project is focused on creating a song recommendation system for a series of basic everyday activities for various listening styles. The goal is to provide a personalized music experience for users and all activities they may do.

## How to Use 

Clone the repo in your local desktop.
Set up authorization manager and update with personal information as referenced below.  
```python
sp = spotipy.Spotify(auth_manager=SpotifyOAuth(scope="playlist-modify-private",
                    client_id='{client id', client_secret='{client secret}',
                    redirect_uri="http://example.com"))

```
Copy and paste desired playlist from your account into the variable labelled playlist_link. 
```python
playlist_link = "{spotify link}"
playlist_URI = playlist_link.split("/")[-1].split("?")[0]
track_uris = [x["track"]["uri"]for x in sp.playlist_tracks(playlist_URI)["items"]]
```


## Spotify API Access
This tool relies on the access to the spotify API in order to read user data and create a playlist. To read more about recieving your personalized key please see https://developer.spotify.com/documentation/web-api. 

The following libaries are required along with a personalised Client API Key, Secret Key, user ID and ID of personal playlist you want the recommendation to be based on. 

```python
import spotipy
from spotipy.oauth2 import SpotifyClientCredentials
from spotipy.oauth2 import SpotifyOAuth

```
## Development Tools 
Juptyer Notebook, Python, Spotify Web API.

## Contributers and Remarks
This is a final project for Winter 2023 SOFE 4620U Machine Learning and Data Mining course at Ontario Tech University. 

Authors include Mitchell Hicks, Michelle Cheng & Tolu Elebute.


