# MusicFinder
#### Video Demo:
https://youtu.be/ftAz_DSzgMQ
#### Description:
MusicFinder is a web application designed to help you identify songs stuck in your head. Just type in a part of the lyrics you remember, and MusicFinder will search for the song title and artist. You can also save your favorite songs to revisit them later.

#### Motivation:
The idea for MusicFinder came from the common experience of having a catchy tune or phrase stuck in your mind without knowing the song's name or artist. This app aims to resolve this by allowing users to search for songs using only a few lyrics, helping them identify the song that has been playing on repeat in their head.

#### Features:
1. Search by lyrics,
2. Favorites,
3. User authentication,
4. Responsive design

#### Technologies used:
1. Flask
2. SQLite
3. CS50 SQL library
4. Bootstrap
5. Jinja2

#### Project structure:
1. ‘app.py’: the main file that the flask run
2. ‘helpers.py’: contains helper functions for common tasks
3. ‘templates/’: HTML templates rendered by Flask, using Jinja2 for dynamic content
4. ‘static/’: static assets like CSS and images
5. ‘musicfinder.db’: SQLite database containing user information, song data, and favorites

#### How It Works:
1. User authentication:
    a. New users can register by providing a username and password. The password is hashed using ‘werkzeug.security’.
    b. Returning users can log in using their username and password. Sessions are used to keep users logged in.
2. Searching for songs:
    a. Once logged in, users are directed to the search page, where they can input a fragment of lyrics they remember.
    b. The app searches the music table in the SQLite database using an SQL query that matches the lyrics with the ‘LIKE’ operator.
    c. Results are displayed in a table with the artist and song title.
3. Adding to favorites:
    a. Users can add any search result to their favorites by clicking a button. After the song is successfully added to the database, the page will give the user a prompt saying ‘Added to My Favorites’.
    b. The favorite songs are stored in the ‘favorites’ table, associated with the user’s ID.
4. Viewing favorites:
    a. Users can view their favorite songs at any time by clicking on the ‘Favorites’ link in the navigation bar.

#### Challenges:
The hardest challenge was adding songs to the favorite list without reloading the page. This was achieved using an AJAX request to handle the ‘POST’ request for adding songs, updating the user interface dynamically.

#### Future improvements:
1. Add features to help users who forgot their password and/or username.
2. Integration with Spotify API or other external music APIs: automatically get updated song database, automatically add identified songs to a Spotify playlist.
3. Implement a more advanced lyric-finding algorithm for better search accuracy.
4. Enhance the user interface with additional styling and interactive elements.
