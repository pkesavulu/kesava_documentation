# CURL:-
---

> curl transfer data from server using one of the protocols like HTTP,HTTPS,FTP,FTPS,SCP, SCP, SFTP, TFTP, DICT, TELNET, LDAP or FILE. (To transfer multiple files use wget or FTP.)

> Use the specified HTTP proxy. If the port number is not specified, it is assumed at port 1080.

```

-x host:port

-x [protocol://][user:password@]proxyhost[:port]

--proxy [protocol://][user:password@]proxyhost[:port]

```

By default you use curl without explicitly saying which request method to use. If you just pass in a HTTP URL like curl http://example.com it will use GET. If you use -d or -F curl will use POST, -I will cause a HEAD and -T will make it a PUT.

If for whatever reason you're not happy with these default choices that curl does for you, you can override those request methods by specifying -X [WHATEVER]. This way you can for example send a DELETE by doing curl -X DELETE [URL].

Ex:-
---

curl -XGET [URL] as GET would be used anyway. 

```
curl -XGET http://localhost:9200/index/type

```

In the same way to do curl -X POST -d data [URL]... But you can make a fun and somewhat rare request that sends a request-body in a GET request with something like curl -X GET -d data [URL].




