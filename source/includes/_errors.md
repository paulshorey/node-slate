# Errors  
  
<aside class=error>  
This error section is stored in a separate file in `includes/_errors.md`. Slate allows you to optionally separate out your docs into many files...just save them to the `includes` folder and add them to the top of your `index.md`'s front matter. Files are included in the order listed.  
</aside>  
  
The Kittn API uses the following error codes:  
  
  
Error Code | Meaning  
---------- | -------  
400 | Bad Request -- The request could not be understood by the server due to malformed syntax.  
401 | Unauthorized -- Your API key is wrong.  
403 | Forbidden -- The kitten requested is hidden for administrators only.  
404 | Not Found -- The specified kitten could not be found.  
405 | Method Not Allowed -- You tried to access a kitten with an invalid method.  
406 | Not Acceptable -- You requested a format that isn't JSON.  
410 | Gone -- The kitten requested has been removed from our servers.  
418 | I'm a teapot.  
429 | Too Many Requests -- You're requesting too many kittens! Slow down!  
500 | Internal Server Error -- We had a problem with our server. Try again later.  
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.  
