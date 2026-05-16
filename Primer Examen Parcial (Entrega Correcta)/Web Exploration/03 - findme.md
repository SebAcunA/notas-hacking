#### Descripción 
Help us test the form by submiting the username as `test` and password as `test!`
The website running [here](http://saturn.picoctf.net:58127/).
#### Solución
```
* Ignoring the response-body

* Connection #0 to host saturn.picoctf.net left intact

* Issue another request to this URL: 'http://saturn.picoctf.net:58127/next-page/id=cGljb0NURntwcm94aWVzX2Fs'

* Switch from POST to GET

* Found bundle for host: 0x600000c588d0 [serially]

* Can not multiplex, even if we wanted to

* Re-using existing connection with host saturn.picoctf.net

> GET /next-page/id=cGljb0NURntwcm94aWVzX2Fs HTTP/1.1

> Host: saturn.picoctf.net:58127

> User-Agent: curl/8.7.1

> Accept: */*

> 

* Request completely sent off

< HTTP/1.1 200 OK

< X-Powered-By: Express

< Content-Type: text/html; charset=utf-8

< Content-Length: 264

< ETag: W/"108-p43QX15azZA05imtghrPlRHx7LY"

< Date: Fri, 15 May 2026 23:04:19 GMT

< Connection: keep-alive

< Keep-Alive: timeout=5

< 

<!DOCTYPE html>

<head>

    <title>flag</title>

</head>

<body>

    <script>

        setTimeout(function () {

           // after 2 seconds

           window.location = "/next-page/id=bF90aGVfd2F5XzI1YmJhZTlhfQ==";

        }, 0.5)

      </script>

    <p></p>

* Connection #0 to host saturn.picoctf.net left intact

</body>**%**                                                                                                                                                                             rosyperez@MacBookAir notas-hacking %
```
#### Notas
La bandera está compuesta por dos redireciciones encriptada en base 64
#### Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnR3Y205NGFXVnpYMkZzYkY5MGFHVmZkMkY1WHpJMVltSmhaVGxoZlE9PQ