# Add a input `form` to the UI [(YouTube 12:10)](https://youtu.be/qtOmufIjafE?t=730%20%E2%80%8B)

The image contains the `form`, `function` and `debug`node, we will create.

![](../images/search-data-01-g.png)

### Step 1: Configure the UI input `form`

![](../images/add-input-form-00.png)

### Step 2: Configure the UI input `form`

Remember the structure of the UI elements.

![](../images/setup-ui-00-a.png)

* Add a group with the name `user`

![](../images/add-input-form-01.png)

* Add a tab with the name `Home` and press add

![](../images/add-input-form-02.png)

* Press add

![](../images/add-input-form-03.png)

* Give the UI from a name `Insert a new User` and add the input fields for firstname, lastname and country

![](../images/add-input-form-04.png)

* Add a `function` node and insert following code and wire the nodes

The code ensures that the data will be save in the right JSON format we need.

```javascript
var data = {};
data.user = msg.payload;
msg.payload = data;
return msg;
```

![](../images/add-input-form-07.png)

* Press `Deploy

### Step 7: Open in a new browser tab `https://[your-host]/ui/`

![](../images/add-input-form-05.png)

### Step 8: Insert a name and press `SUBMIT`

![](../images/add-input-form-08.png)

### Step 9: Now wire the function as input for the database

![](../images/add-input-form-09.png)

### Step 10:Press `Deploy`

