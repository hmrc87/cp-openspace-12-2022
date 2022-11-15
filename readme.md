# Conplement Openspace 08.12.2022 NGINX-Example
This repository demonstrates basic features of nginx like reverse proxying requests to another local service or serving static pages.

[nginx.conf](nginx.conf) contains the main configuration for nginx. Here you can define modules that are loaded or logger settings. It also includes the application specific [default.conf](default.conf).



After you started both containers open your browser with *localhost:80* and you should see the static page. This is served by nginx directly. One could use this to serve static pages like a blog or a simple website.

When you open your browser and point to *localhost:80/api/logs* you should see the logs of the api container. This is done by nginx reverse proxying the request to the api container.


## How to run
1. Clone this repository
2. Run nginx ``` docker compose -f docker-compose ``` 
3. Open http://localhost in your browser
4. Explore the  [default.conf](default.conf) locations from your browser and see what happens!
5. Optionally check the nginx logs with ``` docker logs -f nginx-example ```
6. If you change the default.conf you need to reload the nginx config. This can be done with ``` docker exec -it nginx-example nginx -s reload```


# Good links
https://stackoverflow.com/questions/38228393/nginx-remove-html-extension