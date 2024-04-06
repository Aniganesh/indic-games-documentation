# Infra

Diagram representing current infrastructure (disable dark mode to view png properly):

![infra drawio](https://github.com/Aniganesh/indic-games-documentation/assets/47713754/4d298356-dfbc-429f-92cd-d6d8882c2b99)

## Explanation
When a request comes in, NGINX configuration checks the user agent to see if it is a crawler. The checking logic is from prerender's config over [here](https://github.com/prerender/prerender-nginx/blob/master/nginx.conf). If the request is from a crawler, then nginx redirects the request to a lambda service with the url as the payload. Otherwise the local files are served by nginx directly. This is done for SEO purposes as crawlers don't execute the js and website is a React SPA.

The lambda service in turn, checks if there is an entry in the Redis database for the requested url and return the html stored in the db. If not, it uses Puppeteer to visit the url, wait for the content to load, save the html content to redis against that url and then returns the content.
