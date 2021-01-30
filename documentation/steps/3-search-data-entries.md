# Search for the entries

To search for data entries in our Cloudant database, we need to create a design document to define a [search index](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-query) we will use in our queries.
We will create file additional nodes. Three `inject`, two `cloudant in` and one `debug` node.

![](../images/search-data-01-b.png)

_Note:_ When we will query for data we need to ensure we save the data in the right format.

## Configure a search index

We need to create a design document to define a [search index](https://cloud.ibm.com/docs/Cloudant?topic=Cloudant-query) we will later use our queries.

* theFirstname
* theLastname
* theCountry

Example usage of a query `theLastname:S*` later:

![](../images/search-data-01-a.png)

### Step 1: Open the Cloudant the created database `absolute-beginner`

![](../images/search-data-01-c.png)

### Step 2: Create a new design document

![](../images/search-data-01-d.png)

### Step 3: Insert following JSON to create the needed design document

```json
{
  "_id": "_design/_d_searchindex",
  "views": {},
  "language": "javascript",
  "indexes": {
      "_searchindex": {
        "analyzer": "standard",
        "index": "function (doc) {\n  index(\"default\", doc._id);\n\n  if(doc.user.firstname){\n    index(\"theFirstname\", doc.user.firstname, {\"store\": true, \"facet\":true});\n  }\n  if(doc.user.lastname){\n    index(\"theLastname\", doc.user.lastname, {\"store\": true, \"facet\":true });\n  }\n  if(doc.user.country){\n    index(\"theCountry\", doc.user.country, {\"store\": true, \"facet\":true});\n  }\n}"
    }
  }
}
```
The image shows the new design document. 

![](../images/search-data-01-e.png)

### Step 4: Open the search index `_searchindex` and insert in query "theFirstname:T*", then press query

![](../images/search-data-02.png)

### Step 5: Configure the three `inject nodes`

* Search for Firstname

```json
{
    "theFirstname": "T*",
    "limit": "200"
}
```

* Search for Lastname

```json

{
    "theLastname": "S*",
    "limit": "200"
}
```

* Search for Country

```json
{
    "theContry": "S*",
    "limit": "200"
}
```

![](../images/search-data-03.png)

### Step 6: Configure the new `cloudant in` node

* Database: `absolute-beginner`
* Search by: `search index`
* Design document: `_d_searchindex`
* Index name: `_searchindex`

![](../images/search-data-01-f.png)
