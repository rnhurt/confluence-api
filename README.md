# Confluence API
This project contains a Node.js module which wraps Atlassian's [Confluence API](https://docs.atlassian.com/atlassian-confluence/REST/latest/).

## Getting Started
Install confluence-api via npm:
```
$ npm install confluence-api
```

Create an instance of Confluence by providing a username and password (Confluence uses basic http authentication) and a baseUrl used for all future requests.  For instance:
```javascript
var Confluence = require("../lib/confluence");
var config = {
    username: "testuser",
    password: "test-user-pw",
    baseUrl:  "https://confluence-api-test.atlassian.net/wiki"
};
var confluence = new Confluence(config);
confluence.getContentByPageTitle("space-name", "page-title", function(err, data) {
  // do something interesting with data; for instance,
  // data.results[0].body.storage.value contains the stored markup for the first
  // page found in space 'space-name' matching page title 'page-title'
}
```

Confluence currently exposes the following API...

<a name="Confluence"></a>
## Confluence
**Kind**: global class  
**this**: <code>{Confluence}</code>  

* [Confluence](#Confluence)
  * [new Confluence(config)](#new_Confluence_new)
  * [.getSpace(space, callback)](#Confluence+getSpace)
  * [.getSpaceHomePage(space, callback)](#Confluence+getSpaceHomePage)
  * [.getContentById(id, callback)](#Confluence+getContentById)
  * [.getContentByPageTitle(space, title, callback)](#Confluence+getContentByPageTitle)
  * [.postContent(space, title, content, parentId, callback)](#Confluence+postContent)
  * [.putContent(space, id, version, title, content, callback)](#Confluence+putContent)
  * [.deleteContent(id, callback)](#Confluence+deleteContent)

<a name="new_Confluence_new"></a>
### new Confluence(config)
Construct Confluence.


| Param | Type |
| --- | --- |
| config | <code>Object</code> | 
| config.username | <code>string</code> | 
| config.password | <code>string</code> | 
| config.baseUrl | <code>string</code> | 

<a name="Confluence+getSpace"></a>
### confluence.getSpace(space, callback)
Get space information.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type |
| --- | --- |
| space | <code>string</code> | 
| callback | <code>function</code> | 

<a name="Confluence+getSpaceHomePage"></a>
### confluence.getSpaceHomePage(space, callback)
Get space home page.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type |
| --- | --- |
| space | <code>string</code> | 
| callback | <code>function</code> | 

<a name="Confluence+getContentById"></a>
### confluence.getContentById(id, callback)
Get stored content for a specific space and page title.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type |
| --- | --- |
| id | <code>string</code> | 
| callback | <code>function</code> | 

<a name="Confluence+getContentByPageTitle"></a>
### confluence.getContentByPageTitle(space, title, callback)
Get stored content for a specific space and page title.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type |
| --- | --- |
| space | <code>string</code> | 
| title | <code>string</code> | 
| callback | <code>function</code> | 

<a name="Confluence+postContent"></a>
### confluence.postContent(space, title, content, parentId, callback)
Post content to a new page.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type | Description |
| --- | --- | --- |
| space | <code>string</code> |  |
| title | <code>string</code> |  |
| content | <code>string</code> |  |
| parentId | <code>number</code> | A null value will cause the page to be added under the space's home page |
| callback | <code>function</code> |  |

<a name="Confluence+putContent"></a>
### confluence.putContent(space, id, version, title, content, callback)
Put/update stored content for a page.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type |
| --- | --- |
| space | <code>string</code> | 
| id | <code>string</code> | 
| version | <code>number</code> | 
| title | <code>string</code> | 
| content | <code>string</code> | 
| callback | <code>function</code> | 

<a name="Confluence+deleteContent"></a>
### confluence.deleteContent(id, callback)
Delete a page.

**Kind**: instance method of <code>[Confluence](#Confluence)</code>  

| Param | Type |
| --- | --- |
| id | <code>string</code> | 
| callback | <code>function</code> | 

<a name="request"></a>
## request
Node.js wrapper for Atlassian's Confluence API.
See https://developer.atlassian.com/confdev/confluence-rest-api

Copyright (c) 2015, John Duane
Released under the MIT License

**Kind**: global variable  