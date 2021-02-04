# Get data entries [YouTube (5:54)](https://youtu.be/qtOmufIjafE?t=351%20%E2%80%8B)

Now we will load all existing data entries from our Cloudant database.
We will use a simple configuration.

### Step 1: Add a `inject`,  a `cloudant in` and a `debug` node to the flow

![](../images/get-data-00-a.png)

### Step 2: Wire the nodes and configure the `cloudant in` node

* Database: `absolute-beginner`
* Search by: `all documents`

![](../images/get-data-00.png)

### Step 3: Press deploy

### Step 4: Press the newly created `inject` node and watch the output in the debug tab

![](../images/get-data-01.png)

