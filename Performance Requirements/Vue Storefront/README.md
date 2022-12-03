
# Usage of Cache

Caching is a temporary storage mechanism that allows websites to load information faster. Instead of accessing the database directly, the website will access the cached version and pull the necessary information from the server memory.

Cached data are files, scripts, images, and other multimedia stored on your device after opening an app or visiting a website for the first time. This data is then used to quickly gather information about the app or website every time revisited, reducing load time.

### Vue Storefront Architechure

![Vue Cache](https://i.imgur.com/jK8Yvjz.png)

The cache can and should be enabled on all Vue Storefront layers: including client (Service Worker), vue-storefront-api (nginx output cache) and vue-storefront app (SSR output cache).

### SSR Output Cache

Vue Storefront supports a very efficient Server Side Rendering cache. In this mode, the generated HTML pages are fully stored in the Redis cache. The cache entries are then tagged with all the products, categories (and potentially other data entities) used to render that specific page.

Let’s say the Category page contains 20 products products = [{ id: 120, ... }, { id: 324, ... }, ...] after this specific category page got rendered, Vue Storefront would tag the output cache entry with the following tags: P120, P324, C56 (… if the category id was 56).

Each time, Vue Storefront indexers (both: mage2vuestorefront and magento2-vsbridge-indexer) are pushing the changes for any of the tagged product to Elastic storage, the indexer is calling an URL like: https://your-instance.com/invalidate?tags=P120. This request invalidates cache, assigned to this specific product. There is no risk the user will get any outdated product information.

### API output cache

Although the SSR cache is pretty cool — even when it’s enabled, the cache hit ratio still would be pretty low. It’s because most of the requests are executed in CSR (client-side mode), querying the API directly from the client's browser. If you’re facing any Elastic performance issues or it’s high on resources that you’d like to limit— it’s a time to introduce the API output cache.

We’re recommending to put an nginx or varnish proxy in front of vue-storefront-api. With such a proxy, adding the API cache is pretty easy.

     location /api/ {
            proxy_pass https://vue-storefront-api:8080/api/;
        }

..

    location /api/catalog/ {
            proxy_pass https://vue-storefront-api:8080/api/catalog/;
            proxy_cache static;
            proxy_cache_valid 200 1h;
            proxy_cache_methods GET HEAD POST;
            proxy_cache_key "$scheme$proxy_host$request_uri|$request_body";
        }


