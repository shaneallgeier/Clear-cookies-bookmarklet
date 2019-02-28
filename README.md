# Clear Cookies

Clear the cookies for a domain and all subdomains.

## Installation

1) Create a new bookmark on your web browser's bookmark bar. For example, in Chrome, right-click the bookmark bar and choose "Add Page...". 

2) Name the bookmark something like "Crumble Cookies", and then for the URL, paste the following:
```javascript
javascript:var numCookies=0; var cookieArray=document.cookie.split("; "); for(var i=0; i<cookieArray.length && cookieArray[i]; i++) {numCookies++; for(var subDomain= "." + location.host; subDomain; subDomain=subDomain.replace(/^(?:%5C.|[^%5C.]+)/, "")){ for(var curPath =location.pathname; curPath; curPath=curPath.replace(/.$/,"")){document.cookie=(cookieArray[i] + "; domain=" + subDomain + "; path=" + curPath + "; expires="+new Date((new Date()).getTime()-1e11).toGMTString());}}} alert("I crumbled " + numCookies + " cookies for you!"); window.location.href = "http://" + window.location.host + window.location.pathname;
```

## Usage
When you are on a page and don't want it to remember who you are anymore, click Crumble Cookies. All cookies for that domain will be expired immediately, and the page will be reloaded.
