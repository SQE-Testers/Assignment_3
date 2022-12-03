
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

### Lazy Loading in Magento:
![lazy Loading Magento](https://cm.magefan.com/mf_webp/gif/media/catalog/magento-lazy-loading.webp)

# Usage of PWA

Progressive Web Application (PWA) is a type of web app that can operate both as a web page and mobile app on any device. It is a great solution for poor mobile UX and low conversion rates in your online store. Using standard technologies, PWA is aimed at delivering native-like user experience, with speedier conversion and cleaner browsing even with a poor Internet connection.

![lazy Loading Magento](https://i.imgur.com/jCnIAJj.png)

### PWA used in Magento

A PWA Studio storefront application communicates with Magento using its external API. These external API services interact with Magento’s internal service modules and return the response through the same external API. GraphQL is the preferred API for this purpose (fetch and push data).

![lazy Loading Magento](https://i.imgur.com/sYWTBHG.png)


PWA is installed in Magento using Venia storefront (PWA storefront). The coupling between a PWA Studio storefront and Magento should be such that the storefront has a dependency on Magento, but not vice versa. A PWA Studio storefront and its backing Magento server are two independent applications. Therefore, unlike Magento themes (which has its codebase in Magento), PWA’s codebase is separate from each other.

PWA is integrated with Magento using the following major steps:

- Cloning the PWA studio repository
- Installing the PWA studio dependencies
- Specifying the Magento backend server

Magento's front-end themes such as assets, scripts, layout files, etc. are not used by PWA studio storefront. Instead, PWA studio uses its own storefront applications to build front-end store and uses Magento’s GraphQL and REST APIs to send or receive data.


# Usage of Service Workers

Web Workers are a simple means for web content to run scripts in background threads. The worker thread can perform tasks without interfering with the user interface. Once created, a worker can send messages to the JavaScript code that created it by posting messages to an event handler specified by that code (and vice versa).


![workers](https://i.imgur.com/wRF3fpO.png)

The main thread creates the worker using the “Worker” constructor. This constructor takes in a single argument, the path to the worker file. The worker file contains the code that will run in the worker thread; workers run in another global context that is different from the current window.

Data is passed between the worker and the main thread via messages — the main thread and worker thread sends messages using the postMessage() method, and respond to messages sent using the onmessage handler.


# Use of Local storage

Local storage can store 5MB of data per app for the lifetime of the app. Closing the browser will not affect the data in any way – it stays there unless you delete it.

You can only access the local storage object through localStorage. The methods you can use to perform operations on the localStorage object are:

    localStorage // to access the localStorage object 
    localStorage.setItem('name', 'John') // sets name equal to john localStorage.getItem('name') // "John" 
    localStorage.removeItem('name') // removes name from the localStorage localStorage.clear() // clears the localStorage

localStorage.setItem() takes a key and value as parameters and sets a new item in the local storage object equal to the given key value pair.

localStorage.getItem() takes a key as a parameter and returns the value stored to that key in the storage.

localStorage.clear() clears the whole localStorage object.

localStorage.removeItem() takes in a key as a parameter and removes the corresponding key-value pair. ‌‌

Any item that you store in localStorage will be stored as a string. This means that you need to convert other data types such as arrays or objects to strings – otherwise you lose their structure.

See the example below:      

    const scores = [10, 8, 6, 3, 9] 
    const scoresJSON = JSON.stringify(scores) 
    localStorage.setItem('scores', scoresJSON) 
    localStorage // output >> {scores: '[10, 8, 6, 3, 9]', length: 1}

In the example above, we first created an array score, then converted it into a string using JSON.stringify(), and finally saved the stringified scores array in localStorage.

![workers](https://i.imgur.com/Sa2Uzha.png)


