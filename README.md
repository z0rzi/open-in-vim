# Open in Vim - Chrome DevTools Extension
This is an extension for Google Chrome to open resources from the Dev Tools (like CSS, SCSS, JS files) directly inside your Vim Editor
<br/>
<br/>
![Screenshot](design/screenshot.png)
<br/>
<br/>
## Installation

1. Install the extension from the Chrome Web Store:<br/>
???????

2. Now you can right-click on any file link in Chrome Devtools and select "Open using Open In Vim".<br/>
If you want to open all files in Vim automatically, open Chrome DevTools, go to Settings. Under *Extensions* -> *Link Handling* select *Open In Vim*.
![Linkhandling](src/tutorial-linkhandling.png).<br/>


3. Open one of your projects in your Vim IDE (WebStorm, PHPStorm etc.). 
<br/> Open the corresponding website in Chrome, inspect it, right-click on any resource and select *Open in Vim*.<br/>
Now the resource will be opened in your IDE.

4. If the web root of your Vim project is different from your project root, you have to do one the following methods in order for this extension to work:
	- Method 1: In Vim right-click on the the directory that is the web root of the project and select *Mark directory as* -> *Sources Root*
	- Method 2: In Chrome go to chrome://extensions/ -> Open In Intellij -> Options. Under *Root Paths* set up the path mappings for your project. For example, if your site is www.yoursite.com (live) and yoursite.priv (local)) and within your Vim project the web root for this site is under dist/web/, enter those site names under *Site* and the path under *Root Path*.

<br/>

## Troubleshooting
If the links don't open in your IDE, try one or more of the following steps:
<br/>
- Restart Chrome and your Vim IDE. It never hurts to turn things off and on again.

- Read the debug messages: Make sure the Devtools are undocked into a separate window (open the three-dot Chrome Devtools settings menu and select the first icon from "Dock side"). Then inspect the current DevTools window by pressing Ctrl+Shift+I (Windows) or Option+Command+I (Mac). Yes, you can actually inspect the DevTools window itself. Switch to the console tab, there will be debug messages from this extension like 'Open In Vim - received open resource event'. This may help with your troubleshooting process.

- Go to your Vim/WebStorm/PHPStorm Settings -> Build,Execution,Deployment -> Debugger -> Built-In Server and check  *Allow unsigned requests*.

- With your Vim IDE open, open the following URL in Chrome: http://localhost:63342/ - if you get a 404 Not Found page that means the Vim API is working. <br/>
	Otherwise check the Port in Vim Settings -> Build,Execution,Deployment -> Debugger -> Port. If the port is not 63342 go to your Chrome preferences -> Extensions -> Open In Vim -> Options and adjust the URL under *Built-in Webserver URL*.

- Check if the Vim REST API is working: Open a project in Vim, choose any file and copy the relative path. Now in Chrome try to open *http://localhost:63342/api/file?file=path/to/file.js*, where you replace the file parameter with the path you just copied. If that doesn't open the file in Vim there is a problem with the Vim API on your machine.

- Make sure to check if you need to set up any path mappings (See instructions step 4)

