Steps to replay tests

1. Install Newman, use this link will help: https://blog.postman.com/installing-newman-on-windows/
- if you have nodejs installing run this command instead:
- npm install -g newman

2.Pull this repository to a folder

3. Go to Spotify for developers, and generate an OAuth token, e.g. from a link such as https://developer.spotify.com/console/get-album/?id=0sNOF9WDwhWunNAHPD3Baj

- in the permissions include the permissions that you want to be checked, e.g. user-top-read will allow you to test the user based requests

4. In the folder with the repository, open up the globals file using notepad, and in the Auth section, replace the token with your newly created token

5. Open up Powershell, (run 'newman -v' to check newman is installed)

- run the command: newman run 'x.postman_collection.json -g SpotifyWorkspace.postman_globals.json' where x is the type of collection you want to be run

The tests for response should pass