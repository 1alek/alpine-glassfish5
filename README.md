alpine-glassfish5
================

Docker image to run a Glassfish 5 application server

Usage
-----

To run the image:
```
docker run -d -p 4848:4848 -p 8080:8080 -p 8181:8181 -p 9009:9009 --name glassfish4 aleksu/alpine-glassfish5
```

Ports:
    4848 (for administration), 8080 (for the HTTP listener), and 8181 (for the HTTPS listener), and 9009 (for tcp jpda debug)

To get admin password:
```
docker logs glassfish5
```

Web admin:
```
http://127.0.0.1:4848/
```

Specific password:
```
docker run -d -p 4848:4848 -p 8080:8080 -e GLASSFISH_PASS="P@ssw0rd" aleksu/alpine-glassfish5
```

You can now test your deployment:
```
http://127.0.0.1:8080/
```

Domains directory:
```
-v /data/domains/:/opt/glassfish5/glassfish/domains/
```
