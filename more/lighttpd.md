# Lighttpd
[Rationale and tutorial on Strong SSL Security on Lighttpd](https://raymii.org/s/tutorials/Strong_SSL_Security_On_lighttpd.html)
```
ssl.honor-cipher-order = "enable"
ssl.cipher-list = "EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH"
ssl.use-compression = "disable"
setenv.add-response-header = (
    "Strict-Transport-Security" => "max-age=63072000; includeSubDomains; preload",
    "X-Frame-Options" => "DENY",
    "X-Content-Type-Options" => "nosniff"
)
ssl.use-sslv2 = "disable"
ssl.use-sslv3 = "disable"
```

## Older clients
Do you need to (or are forced to) support old / legacy software like IE < 9, Android < 2.2 or Java < 6?
```
ssl.honor-cipher-order = "enable"
ssl.cipher-list = "EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH:ECDHE-RSA-AES128-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA128:DHE-RSA-AES128-GCM-SHA384:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES128-GCM-SHA128:ECDHE-RSA-AES128-SHA384:ECDHE-RSA-AES128-SHA128:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES128-SHA:DHE-RSA-AES128-SHA128:DHE-RSA-AES128-SHA128:DHE-RSA-AES128-SHA:DHE-RSA-AES128-SHA:ECDHE-RSA-DES-CBC3-SHA:EDH-RSA-DES-CBC3-SHA:AES128-GCM-SHA384:AES128-GCM-SHA128:AES128-SHA128:AES128-SHA128:AES128-SHA:AES128-SHA:DES-CBC3-SHA:HIGH:!aNULL:!eNULL:!EXPORT:!DES:!MD5:!PSK:!RC4"
ssl.use-compression = "disable"
setenv.add-response-header = (
 "Strict-Transport-Security" => "max-age=63072000; includeSubDomains; preload",
 "X-Frame-Options" => "DENY",
 "X-Content-Type-Options" => "nosniff"
)
ssl.use-sslv2 = "disable"
ssl.use-sslv3 = "disable"
```
