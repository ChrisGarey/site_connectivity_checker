Python Site Connectivity Checker

This site connectivity checker can take one or more URLs at the command line. Then it creates an internal list of target URLs and checks them for connectivity by issuing HTTP requests and processing the corresponding responses.

Using the -a or --asynchronous option makes the application perform the connectivity checks asynchronously, potentially resulting in lower execution times, especially when you’re processing a long list of websites.


    -u or --urls allows you to provide one or more target URLs at the comment line.
    -f or --input-file allows you to supply a file containing a list of URLs to check.
    -a or --asynchronous allows you to run the connectivity checks asynchronously.


By default, the application will run the connectivity checks synchronously. In other words, the app will perform the checks one after another.

With the -a or --asynchronous option, you can modify this behavior and make the app run the connectivity checks concurrently. To do this, it’ll take advantage of Python’s asynchronous features and the aiohttp third-party library.

Running asynchronous checks can make the website connectivity checker faster and more efficient, especially when you have a long list of URLs to check.

Internally, the application will use the standard-library http.client module to create a connection to the target website. Once you have a connection, then you can make an HTTP request to the website, which will hopefully react with an appropriate response. If the request is successful, then you’ll know that the site is online. Otherwise, you’ll know that the site is offline.