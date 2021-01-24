### Step 1: Add a UI input from to the flow

![](../images/add-input-form-00.png)

### Step 2: Configure the UI input from

* Add a group with the name `user`

![](../images/add-input-form-01.png)

* Add a tab with the name `Home` and press add

![](../images/add-input-form-02.png)

* Press add

![](../images/add-input-form-03.png)

* Give UI from a name `Insert a new User` and add the input fields for firstname, lastname and country

![](../images/add-input-form-04.png)

* Add a function node and insert following code and wire the nodes

```javascript
var data = {};
data.user = msg.payload;
msg.payload = data;
return msg;
```

![](../images/add-input-form-07.png)

* Press deploy

### Step 7: Open in a new browser tab `https://your-host/ui/

![](../images/add-input-form-05.png)


### Step 8: Insert a name and press `SUBMIT`

![](../images/add-input-form-08.png)

### Step 9: Now wire the function as input for the database

![](../images/add-input-form-09.png)

