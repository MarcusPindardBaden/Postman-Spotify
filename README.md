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

If it doesn't, then check the token has the right permissions and has been entered in fully, or that newman has been installed globally

6. Now run the command 'npm install -g newman-reporter-htmlextra', this will install a reporter so that you can view results easier

7. Run the command:
'newman run UserBasedRequests.postman_collection.json -g SpotifyWorkspace.postman_globals.json -r htmlextra --reporter-htmlextra-title "Automated test reporting - Postman echo"'

- The code will run but nothing will appear in the command line, check the folder with the repository in, you will see a new folder called 'newman'
- In this folder will be the report to open, you can see the response body also containing the results of the check



If you run the PlaylistsBasedRequests, then check your spotify and you should have a new playlist added to it.