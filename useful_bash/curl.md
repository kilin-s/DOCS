 #CURL

cURL supports formatted output for the details of the request (see the cURL manpage for details, under -w, –write-out <format>). For our purposes we’ll focus just on the timing details that are provided.

Create a new file, curl-format.txt, and paste in:

```

    time_namelookup:  %{time_namelookup}\n
       time_connect:  %{time_connect}\n
    time_appconnect:  %{time_appconnect}\n
   time_pretransfer:  %{time_pretransfer}\n
      time_redirect:  %{time_redirect}\n
 time_starttransfer:  %{time_starttransfer}\n
                    ----------\n
         time_total:  %{time_total}\n
 ```
 
Make a request:

curl -w "@curl-format.txt" -o /dev/null -s "http://wordpress.com/"


What this does:
-w "@curl-format.txt" tells cURL to use our format file
-o /dev/null redirects the output of the request to /dev/null
-s tells cURL not to show a progress meter
"http://wordpress.com/" is the URL we are requesting. Use quotes particularly if your URL has "&" query string parameters


```
And here is what you get back:
   time_namelookup:  0.001
      time_connect:  0.037
   time_appconnect:  0.000
  time_pretransfer:  0.037
     time_redirect:  0.000
time_starttransfer:  0.092
                   ----------
        time_total:  0.164
 ```



curl -w "@%~dp0curl-format.txt" -o NUL -s %*
Then you can simply call...

curltime wordpress.org
