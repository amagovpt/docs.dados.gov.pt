---
title: API Tutorial
keywords:
description: API Tutorial
reuses:
datasets:
---

API Tutorial
======================

This page describes the behaviour of the free and open API of this site.

Authentication
----------------

In order to perform write operations, you must first be authenticated and obtain an API key in your profile settings.

This key must be provided on every call in the `X-API-KEY` HTTP header.

Permissions
-------------

API calls are subject to the same permissions as the web interface.

For example, you must be a member of the organisation to modify any of its datasets.

Pagination
----------

Some methods are paginated and follow the same pagination model. The list of objects is encapsulated in a `Page` object.

You don't have to calculate the previous and next pages yourself as the URLs are available in the response in the `previous_page` and `next_page` attributes. They will be set to `null` if there is no previous and/or next page.

Example:

    {
                    "data": [{...}, {...}],
                    "page": 1,
                    "page_size": 20,
                    "total": 10,
                    "next_page": "https://data.public.lu/api/endpoint/?page=2",
                    "previous_page": null
                }


## Examples 

The following examples use the following command line tools: [httpie](http://httpie.org) and [jq](http://stedolan.github.io/jq/). You can of course use this API with the tools or libraries of your choice.

### Check that httpie is working

Once httpie is installed, you can check that it is working as expected by typing this command in your terminal:

    $ http 'https://data.public.lu/api/1/organizations/?page_size=1'

This should return a response like this:

    
                HTTP/1.1 200 OK
                Access-Control-Allow-Credentials: true
                ... LOTS OF HEADERS ...
                
                {
                    "data": [
                        {
                
                            ... LOTS OF DATA ...
                
                            "name": "Stelareum",
                            "page": "https://data.public.lu/organizations/stelareum/",
                            "slug": "stelareum",
                            "uri": "https://data.public.lu/api/1/organizations/5cb1d1ed0f7fb0438df74602/",
                            "url": "https://www.stelareum.io/"
                        }
                    ],
                    "next_page": "https://data.public.lu/api/1/organizations/?page=2&page_size=1",
                    "page": 1,
                    "page_size": 1,
                    "previous_page": null,
                    "total": "10"
                }
                

This is very verbose and we don't need all that information right now. That's why we use jq.

### Checking jq is working

Once jq is installed, you can check that it is working by typing this command in your terminal:

    $ http 'https://data.public.lu/api/1/organizations/?page_size=1' | jq '.data[].name'

This should return a response like this:

    "Stelareum"

This is much better! Now that everything is working fine, let's reduce the size of our command line a bit:

    $ export API="https://data.public.lu/api/1/"

The previous command is now equivalent to the more readable command (don't forget the apostrophes):

    $ http $API 'organizations/?page_size=1' | jq '.data[].name'

That's a good start, now let's dive into the API itself. We don't know it yet but we've already retrieved our first organisation.

### Browsing and retrieving data

You can retrieve a list of organisations (filtered or not) or a single organisation. When retrieving an access point, the default number of items per page is 20. Let's retrieve the first 20 organisations via the API:

    $ http $API'organizations/' | jq '.data[].name'

    
                "Stelareum"
                "Department of Public Works - MMTP"
                "NEXXTLAB S.A."
                "Legato Team"
                Legato Team uni.lu" "Legato Team uni.lu
                "Service National de la Jeunesse" "OpenAgenda
                "OpenAgenda" "toto
                "toto
                "Luxembourg Independent Broadcasting Authority" "Centre de gestion informatique de l'éducation
                "Centre de gestion informatique de l'éducation".
                
                

It's good to have this list, but what happens if we want to browse the returned organisations? Let's get the first 5 URIs of organisations.

    $ http $API 'organizations/?page_size=5' | jq '.data[].uri'

    
                "https://data.public.lu/api/1/organizations/5cb1d1ed0f7fb0438df74602/"
                "https://data.public.lu/api/1/organizations/5c403e1528c4b2621cd384e9/"
                "https://data.public.lu/api/1/organizations/5b5b26157676667aa7f57afe/"
                "https://data.public.lu/api/1/organizations/5953ebee111e9b2a8e7133bd/"
                "https://data.public.lu/api/1/organizations/5953d44c111e9b2a5fcb4b59/"
                
                

Now we are able to retrieve an organisation only via the returned URI.

    $ http $API'organizations/5cb1d1ed0f7fb0438df74602/' | jq '.'

That's a lot of data to go through. Let's refine this data, if we only want to extract the metrics:

    $ http $API 'organizations/5cb1d1ed0f7fb0438df74602/' | jq '.metrics'

    
                {
                 "datasets": 0,
                 "members": 1,
                 "views": 0,
                 "followers": 0,
                 "reuses": 0,
                 "dataset_views": 0,
                 "reuse_views": 0,
                 "resource_downloads": 0,
                 
                }
                

Or maybe just the names of the members of this organisation:

    $ http $API'organizations/5cb1d1ed0f7fb0438df74602/' | jq '.members[].user.last_name'

    
                "Crypto"
                
                
It is really up to you to retrieve the relevant data for your project. Feel free to consult [jq's tutorial](http://stedolan.github.io/jq/tutorial/) and [his manual](http://stedolan.github.io/jq/manual/) if you want to browse the API via the command line in more detail.

### Editing and deleting data

Beware, you are entering a danger zone. Modifications and deletions of data via the API are final and we do not provide a sandbox to test before executing them (yet). Be aware of these responsibilities before using your superpowers.

If you attempt to modify a resource without the authentication token, a 401 error will be returned:

    $ http PUT $API'organizations/organization-uri-x/'

    
                HTTP/1.1 401 UNAUTHORIZED
                ... LOTS OF HEADERS ...
                
                {
                    "message": "Unauthorized",
                    "status": 401
                }
                

You must specify your API Key (see above) and use the HTTP header `X-API-KEY`. If you attempt to modify a resource you do not control, a 400 error will be returned:

    $ http PUT $API'organizations/organization-uri-x/' X-API-KEY:your.api.key.here

    
                HTTP/1.1 401 UNAUTHORIZED
                ... LOTS OF HEADERS ...
                
                {
                    "message": "Invalid API Key",
                    "status": 401
                }
                

This is the message you will get if you have specified the wrong API key. This is another potential error message you may encounter.

    
                HTTP/1.1 403 FORBIDDEN
                ... LOTS OF HEADERS ...
                
                {
                    "message": "You do not have the permission to modify that object.",
                    "status": 403
                }
                

This happens if you try to access a resource that you cannot edit with your credentials. If your key is valid you should get something like this:

    
                HTTP/1.1 200 OK
                ... LOTS OF HEADERS ...
                
                {
                    ...
                }
                

But that doesn't change everything! It's perfectly normal, we forgot to specify the right data to send to the server.

    $ http PUT $API'organizations/organization-uri-x/' X-API-KEY:your.api.key.here name="Lorem ipsum" description="The quick brown fox jumps over the lazy dog." | jq '{name: .name, description: .description}'

    
                {
                  "name": "Lorem ipsum",
                  "description": "The quick brown fox jumps over the lazy dog."
                }
                

The resource has been modified with your new values. Finally, you can delete a resource with the appropriate HTTP verb (note that no rollback is possible using the API at this time):

    $ http DELETE $API'organizations/organization-uri-x/' X-API-KEY:your.api.key.here

    
                HTTP/1.0 204 NO CONTENT
                ... LOTS OF HEADERS ...
                
                

Once done, you can check that it is effective by sending a GET to the previous URL:

    $ http GET $API'organizations/organization-uri-x/'

    
                HTTP/1.0 410 GONE
                ... LOTS OF HEADERS ...
                
                {
                    "message": "Organization has been deleted",
                    "status": 410
                }
                
                


Have a look at our [examples showing how to use this API in Python](https://github.com/opendatalu/udata-examples), as well as the [reference documentation](/en/docapi).
