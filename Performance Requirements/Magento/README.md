
# Usage of Cache

Caching is a temporary storage mechanism that allows websites to load information faster. Instead of accessing the database directly, the website will access the cached version and pull the necessary information from the server memory.

Cached data are files, scripts, images, and other multimedia stored on your device after opening an app or visiting a website for the first time. This data is then used to quickly gather information about the app or website every time revisited, reducing load time.


Caching is one of the most effective ways to improve website performance. Generally speaking, there are two methods of caching content:

Client-side (browser)
Server-side
Retrieving stored (cached) content from a previous request for the same client instead of requesting files from your server every time someone visits your site is a more efficient use of network bandwidth.

The Magento page cache library contains a simple PHP reverse proxy that enables full page caching out of the box. A reverse proxy acts as an intermediary between visitors and your application and can reduce the load on your server.

We recommend using Varnish, but you can use Magento’s default caching mechanism instead, which stores cache files in any of the following:

File system (You don’t need to do anything to use file-based caching.)
Database
Redis


## Public and private content

Reverse proxies serve “public” or shared content to more than one user. However, most Magento websites generate dynamic and personalized “private” content that should only be served to one user, which presents unique caching challenges. To address these challenges, Magento can distinguish between two types of content:

- Public - Public content is stored server side in your reverse proxy cache storage (e.g., file system, database, Redis, or Varnish) and is available to multiple customers. Examples of public content include header, footer, and category listing.

- Private - Private content is stored client side (e.g., browser) and is specific to an individual customer. Examples of private content include wishlist, shopping cart, customer name, and address. You should limit stored private content to a small portion of the page’s total content.

# Content Delivery network

Content Delivery Network (CDN) is a network of distributed proxy servers worldwide. Proxy servers act as an intermediary between the origin server & the end-user requesting the content.

CDN uses caching & multiple remote points of presence (PoPs) to serve the content quickly to visitors.

The proxy server stores your media files closer to the target audience. Once a request is made, the content is delivered faster to the visitor.

It ensures that the store is readily available to customers as they browse the site pages.

### Imprtance of CDN in Magento

![CDN Magento](https://i.imgur.com/mHTnnjv.png)

### CDN workflow in Magento

- Browser requests media - A page from the store opens in the customer’s browser, and the browser requests the media that is specified in the HTML.

- Request sent to CDN; images found and served - The request is sent first to the CDN. If the CDN has the images in storage, it serves the media files to the customer’s browser.

- Media not found, request sent to Commerce web server - If the CDN does not have the media files, the request is sent to the Commerce web server. If the media files are found in the file system, the web server sends them to the customer’s browser.

These are the steps of configuring the CDN in Magento:
https://experienceleague.adobe.com/docs/commerce-admin/content-design/media/storage/media-storage-content-delivery-network.html?lang=en

# Lazy Loading

Lazy Loading is an on-demand loading technique that aims at optimizing website loading speed through deferred content delivery, images in particular.

The main idea behind the lazy loading is to load only necessary resources at the viewport instead of loading all of them at once. So the website images are loaded only at the visible part of the page while the others — when users scroll down the page. 

Since the system only loads the elements customers need instead of loading the whole page content, speed is increased and the web page is delivered faster. That's exactly what makes lazy loading one of the best options to optimize images in Magento 2.

### Mageplaze Extension for Magento

Mageplaza is the extension marketplace for Magento 2 where will be downloading SMTP extension for setting up an email configuration with Magento 2.

The Magento Lazy Load extension by Mageplaza helps the development team shorten their web pages’ load time. It doesn’t spend time loading all the product images at once. This results in a significant decrease in the bounce rate.

Magento Lazy Load only loads images within the visible part of the page. Product images that are out of view won’t be loaded until the user explores that particular section by scrolling down.

## Lazy Loading in Magento:
![lazy Loading Magento](https://cm.magefan.com/mf_webp/gif/media/catalog/magento-lazy-loading.webp)

