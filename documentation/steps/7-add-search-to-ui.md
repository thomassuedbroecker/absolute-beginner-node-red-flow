# Add a examle search to UI

Here we will enter search string for our lastname.

![](../images/search-ui-00.png)

### Step 1: Add a UI `form` and `function` Node to the flow

![](../images/search-ui-01.png)

* Insert in the function node and insert following code

```javascript
var data = {};
data.theLastname = msg.payload.lastnamet;
data.limit = "200";
msg.payload = data;
return msg;
}

return msg;
```

### Step 2: Configure the UI `form` 

* Group: `User`
* Label: `Lastname`
* Name: `lastname`

![](../images/search-ui-02.png)

### Step 3: Press deploy
