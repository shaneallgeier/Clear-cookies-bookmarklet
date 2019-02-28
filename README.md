# Clear Cookies

Clear the cookies for a domain and all subdomains.

## Installation

### Recommended method

1) Drag & drop the following link to your browser's bookmark bar: __[Crumble Cookies](javascript:var%20numCookies%3D0%3B%20var%20cookieArray%3Ddocument.cookie.split%28%22%3B%20%22%29%3B%20for%28var%20i%3D0%3B%20i%3CcookieArray.length%20%26%26%20cookieArray%5Bi%5D%3B%20i%2B%2B%29%20%7BnumCookies%2B%2B%3B%20for%28var%20subDomain%3D%20%22.%22%20%2B%20location.hostname%3B%20subDomain%3B%20subDomain%3DsubDomain.replace%28%2F%5E%28%3F%3A%5C.%7C%5B%5E%5C.%5D%2B%29%2F%2C%20%22%22%29%29%7B%20for%28var%20curPath%20%3Dlocation.pathname%3B%20curPath%3B%20curPath%3DcurPath.replace%28%2F.%24%2F%2C%22%22%29%29%7Bdocument.cookie%3D%28cookieArray%5Bi%5D%20%2B%20%22%3B%20domain%3D%22%20%2B%20subDomain%20%2B%20%22%3B%20path%3D%22%20%2B%20curPath%20%2B%20%22%3B%20expires%3D%22%2Bnew%20Date%28%28new%20Date%28%29%29.getTime%28%29-1e11%29.toGMTString%28%29%29%3B%7D%7D%7D%20alert%28%22I%20crumbled%20%22%20%2B%20numCookies%20%2B%20%22%20cookies%20for%20you%21%22%29%3B%20window.location.href%20%3D%20%22http%3A%2F%2F%22%20%2B%20window.location.host%20%2B%20window.location.pathname%3B)__

2) That's it!

### Manual method

1) Create a new bookmark on your web browser's bookmark bar. For example, in Chrome, right-click the bookmark bar and choose "Add Page...". 

2) Name the bookmark something like "Crumble Cookies", and then for the URL, paste the following:
```javascript
javascript:var numCookies=0; var cookieArray=document.cookie.split("; "); for(var i=0; i<cookieArray.length && cookieArray[i]; i++) {numCookies++; for(var subDomain= "." + location.hostname; subDomain; subDomain=subDomain.replace(/^(?:%5C.|[^%5C.]+)/, "")){ for(var curPath =location.pathname; curPath; curPath=curPath.replace(/.$/,"")){document.cookie=(cookieArray[i] + "; domain=" + subDomain + "; path=" + curPath + "; expires="+new Date((new Date()).getTime()-1e11).toGMTString());}}} alert("I crumbled " + numCookies + " cookies for you!"); window.location.href = "http://" + window.location.host + window.location.pathname;
```

## Usage
When you are on a page and don't want it to remember who you are anymore, click Crumble Cookies. All cookies for that domain will be expired immediately, and the page will be reloaded.
