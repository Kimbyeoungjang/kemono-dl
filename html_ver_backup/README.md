# This is just a backup of the html verison please don't use!

# kemono-dl
This is a simple kemono.party downloader using python.

## How to use:
1. Install python
2. Install bs4 using the command ```pip install bs4``` 
3. Download ```kemono-dl.py``` from [releases](https://github.com/AplhaSlayer1964/Kemono.party-Downloader/releases)
4. Get a cookie.txt file from kemono.party 
   - You can get the cookie text file using a [chrome](https://chrome.google.com/webstore/detail/get-cookiestxt/bgaddhkoddajcdgocldbbfleckgcbcid?hl=en) or [firefox](https://addons.mozilla.org/en-US/firefox/addon/cookies-txt/) extension
   - You must pass a cookie file or kemono.party's ddos protection won't let the script access the site 
5. Place users main page link or post link in the Users.txt file with one entry per line
   - links should look like: https://<span></span>kemono.party/SERVICE/user/USERID or https://<span></span>kemono.party/SERVICE/user/USERID/post/POSTID
6. Run ```python kemono-dl.py --cookies "cookie.txt" --user https://kemono.party/SERVICE/user/USERID```


## Options:
- ```-h, --help``` Prints help text then exits
- ```--version``` Displays the current version then exits
- ```--user LINK``` Download user posts
- ```--post LINK``` Download post
- ```--fromfile FILE``` Download users and posts from a file seperated by a newline
- ```-o, --output FOLDER``` Set path to download posts
- ```-a, --archive``` Downloads only posts that are not in archive.txt 
-  ```--cookies FILE``` Set path to cookie.txt (**REQUIRED**)
- ```--date YYYYMMDD``` Only download posts from this date
- ```--datebefore YYYYMMDD``` Only download posts from this date and before
- ```--dateafter YYYYMMDD``` Only download posts from this date and after

## Examples:
- ```python kemono-dl.py --cookies "cookie.txt" -o "C:\Users\User\Downloads" --archive --fromfile Users.txt```
- ```python kemono-dl.py --cookies "cookie.txt" --date 20210101 --user https://kemono.party/SERVICE/user/USERID```
- ```python kemono-dl.py --cookies "cookie.txt" --post https://kemono.party/SERVICE/user/USERID/post/POSTID```

## Notes:
- If no cookie.txt is passed in the script will quit
- If no download location is passed then files will be saved to a ```Downloads``` folder in the current working directory
- Current file format is ```/Serivce_Name/User_name/[Posts date and time] post title/Type/Files```
   - Type refers to ```Downloads```, ```Content```, ```Files```
- In the ```Contents``` folder a folder called ```inline``` will be created to store any images that were embedded in the content section
- External links will be placed in two locations
  - Content_External_Links.txt in the Content folder
  - Files_External_Links.txt in the Files folder
- Using any date option will not downlaod any gumroad posts because they have no dates

## To do:
- [ ] Integrate youtube-dl for downloading external video links
- [ ] Allow file naming structure to be changed in command line
   - [ ] Allow file path structure to be changed in command line
- [ ] Add Discord service
- [ ] Duplicate post name for gumroad might cause error

## Keep in mind:
- Using this might get you IP banned from kemono party.
  - This has not happened to me but is a possibility.
- If the site changes the script might break.