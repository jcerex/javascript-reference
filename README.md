# What is Fetch???? -_-

Fetch API provides a logical way to fetch resources asynchronously across the network using Promises, which enables a simpler and cleaner API, avoiding callback hell and having to remember the complex API of XMLHttpRequest.

The aim of fetch is to provide a modern equivalent to XMLHttpRequest which is an API that gives you the functionality for transferring data between a client and a server. It offers the same sort of functionality but is designed to be more efficient and easier to use.

![That's so fetch](http://res.cloudinary.com/strannikad/image/upload/v1495159590/download_1_wxeilr.gif)

# Why would I use Fetch?

Many websites/apps need to load resources from a remote URL. You may want to make a POST request to a REST API, or you may simply need to fetch a chunk of static content from another server.

The Fetch request is a standard which provides a unified architecture for API interfaces so they are all consistent when it comes to various aspects of fetching, such as redirects and the CORS(cross-origin HTTP request) protocol. This is basically a fancy way of saying to request a resource from a domain or port which is different from the first resource itself serves.

The Fetch Standard also defines the fetch() JavaScript API, which exposes most of the networking functionality at a fairly low level of abstraction.

# How to implement a fetch() request

In order to fetch content from an arbitrary URL, just pass the URL to fetch:
``` javascript
fetch('https://mywebsite.com/mydata.json')
```
Fetch also takes an optional second argument that allows you to customize the HTTP request. You may want to specify additional headers, or make a POST request:
``` javascript
fetch('https://mywebsite.com/endpoint/', {
  method: 'POST',
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    firstParam: 'yourValue',
    secondParam: 'yourOtherValue',
  })
})
```

# What are some potential downfalls of using Fetch?

![Fetchest GIF](http://res.cloudinary.com/strannikad/image/upload/v1495159386/download_hlpid7.gif)


The technologies specification has not stabilized, and the level of compatability for using in various browsers differ, especially around it's use in IE. 

![Support Screen Shot](http://res.cloudinary.com/strannikad/image/upload/c_scale,w_887/v1495159240/Fetch_Support_gx44o6.png)

# What's missing?
Of course, there are some features XHR has that fetch doesn't have.

### Request aborting
This is the big one. In Canary you can cancel the stream, but there's no way to abort a request before headers have arrived.

We're going to fix this using cancellable promises, which other specs will benefit from. Track the discussion of this over at GitHub.

### Progress events
Progress events are a high level feature that won't arrive in fetch for now. You can create your own by looking at the Content-Length header and using a pass-through stream to monitor the bytes received.

This means you can explicitly handle responses without a Content-Length differently. And of course, even if Content-Length is there it can be a lie. With streams you can handle these lies however you want.

### Synchronous requests
Noooope. The fetch spec documents them, but they won't be part of the API. Sync requests are awful.

# Resources

https://jakearchibald.com/2015/thats-so-fetch/

https://developers.google.com/web/updates/2015/03/introduction-to-fetch

https://facebook.github.io/react-native/docs/network.html

https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Basic_concepts

https://fetch.spec.whatwg.org/#preface
