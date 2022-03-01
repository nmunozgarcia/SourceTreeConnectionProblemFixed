# SourceTreeConnectionProblemFixed
The guide which helps me to fix the authentication process in the SourceTree connection to repositories.

# Url to the guide:
https://community.atlassian.com/t5/Sourcetree-questions/Connect-SourceTree-to-2-factor-enabled-GitHub/qaq-p/1743300

# Steps 
I finally made it work.  I will try to summarize as best I can for others needing SourceTree to connect to GIT using 2-factor authentication (2FA):

SourceTree: Tools > Options > Authentication:  Delete as many password accounts as you are able to delete.  Try deleting at least twice for those accounts that are hard to delete.

Close SourceTree.

Windows: Enter Control Panel > User Accounts > Manage Windows Credentials.  Delete all "Git-look-alike" credentials, i.e. the credentials in SourceTree: Tools > Options > Authentication that you were not able to delete.

GitHub:  Set up 2FA.  I used SMS-verification.  Google a bit and you will find a guide.  This step was quite straight-forward.

GitHub:  Create a token: Log in to GitHub, press user drop down arrow at upper right corner, choose 'Settings', choose 'Developer settings', choose 'Personal access tokens', choose 'Generate new token'.  I gave the new token access rights to everything.  Save the token.  My token was a string consisting of 40 characters.

SourceTree: Clear all saved password:  Windows: Go to C:\Users\USERNAME\AppData\Local\Atlassian\SourceTree and remove the 'passwd' file.  The purpose of this step, is to force SourceTree to ask for password in next step.

SourceTree: Open SourceTree and do a Pull Request. SourceTree will now ask for password.  Use the token from (5) as password.