This Node-RED flow is for absolute beginners with minimal `javascript` programming knowledge. 

Covering following main topics:
* saving data
* search for data
* display data in a UI

<https://thomassuedbroecker.github.io/absolute-beginner-node-red-flow/>

# MkDocs installation on mac

### Step 1: Verify the [brew](https://brew.sh) installation

```sh
brew --version
```

### Step 2: Change the folder permission to install python, if needed

```sh
sudo chown -R $(whoami) /usr/local/lib/pkgconfig
chmod u+w /usr/local/lib/pkgconfig
```

### Step 3: Install [python3](https://www.python.org)

```sh
brew install python3
```

### Step 4: Upgrade pip

```sh
pip3 install --upgrade pip
```

### Step 5: Install [mkdocs](https://www.mkdocs.org)

```sh
pip3 install mkdocs
```

### Step 6: 

```sh
python3 -m pip install [mkdocs-material-extensions](https://pypi.org/project/mkdocs-material-extensions/)
```

# Verify your documentation and build the pages

### Step 1: Preview your documentation locally

```sh
python3 -m mkdocs serve  
```

* output:

```sh
INFO    -  Cleaning site directory 
INFO    -  Documentation built in 0.57 seconds 
[I 210125 09:15:48 server:335] Serving on http://127.0.0.1:8000
INFO    -  Serving on http://127.0.0.1:8000
[I 210125 09:15:48 handlers:62] Start watching changes
INFO    -  Start watching changes
[I 210125 09:15:48 handlers:64] Start detecting changes
INFO    -  Start detecting changes
```

### Step 2: Build the pages in the folder "/site", which will be added to your GitHub project

```sh
python3 -m mkdocs build
```

### Step 3: Add folder to `.gitignore`

```sh
echo "site/" >> .gitignore
```



