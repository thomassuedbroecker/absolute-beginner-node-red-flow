This Node-RED flow is for absolute beginners with minimal `javascript` programming knowledge. 

Covering following main topics:
* saving data
* search for data
* display data in a UI

<https://thomassuedbroecker.github.io/absolute-beginner-node-red-flow/>

# How to install MkDocs on Mac and setup integration with GitHub?

The project contains the simplified steps to setup a MkDocs for your GitHub project.

### Local setup:

* [brew](https://brew.sh)
* [Python 3](https://www.python.org)
* [MkDocs](https://www.mkdocs.org)
* [MkDocs Material Extensions](https://pypi.org/project/mkdocs-material-extensions/)

### GitHub: 

* [GitHub CI](https://docs.github.com/en/actions/guides/about-continuous-integration)
* [GitHub Pages](https://pages.github.com)
* [GitHub Branch](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository)


# MkDocs installation on Mac

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

### Step 6: Install the [mkdocs-material-extensions](https://pypi.org/project/mkdocs-material-extensions/)

```sh
python3 -m pip install mkdocs-material-extensions
```

# Verify your documentation and build the pages

### Step 1: Ensure you have a `mkdocs.yml` file in place

This is a example [configuration](https://www.mkdocs.org/user-guide/configuration/):

```yml
# Project information
site_name: Your Project
site_url: https://[YOUR_GITHUB_ID].github.io/[your-repository-name]
site_author: Thomas Südbröcker

# Repository
repo_name: [YOUR-REPOSITORY-NAME]
repo_url: https://github.com/[YOUR_GITHUB_ID]/[YOUR-REPOSITORY-NAME]
edit_uri: edit/master/[YOU-DOCUMENTATION_FOLDER]
docs_dir: [YOU-DOCUMENTATION_FOLDER]

# Navigation
nav:
  - Welcome:
    - Overview: README.md   
  
## DO NOT CHANGE BELOW THIS LINE

# Copyright
# TBD

# Theme
theme:
  name: material
  font:
    text: IBM Plex Sans
    code: IBM Plex Mono
  icon:
    logo: material/library
  features:
    # - navigation.tabs
    - navigation.instant
    - navigation.expand
  palette:
    scheme: default
    primary: blue
    accent: blue

# Plugins
plugins:
  - search

# Customization
# TBD

# Extensions
markdown_extensions:
  - abbr
  - admonition
  - attr_list
  - def_list
  - footnotes
  - meta
  - toc:
      permalink: true
  - pymdownx.arithmatex:
      generic: true
  - pymdownx.betterem:
      smart_enable: all
  - pymdownx.caret
  - pymdownx.critic
  - pymdownx.details
  - pymdownx.emoji:
      emoji_index: !!python/name:materialx.emoji.twemoji
      emoji_generator: !!python/name:materialx.emoji.to_svg
  - pymdownx.highlight
  - pymdownx.inlinehilite
  - pymdownx.keys
  - pymdownx.mark
  - pymdownx.smartsymbols
  - pymdownx.snippets:
      check_paths: true
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
  - pymdownx.tabbed
  - pymdownx.tasklist:
      custom_checkbox: true
  - pymdownx.tilde
```

### Step 1: Preview your documentation locally

```sh
python3 -m mkdocs serve  
```

* Example output:

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

# Integration into your GitHub project

### Step 1: Add folder to `.gitignore`

```sh
echo "site/" >> .gitignore
```

# Integrate the documentation with [GitHub CI](https://docs.github.com/en/actions/guides/about-continuous-integration)

### Step 2: Create a two folders in your project

```sh
mkdir .github
cd .github
mkdir workflows
```

### Step 3: Create a file called `ci.yml` and insert the CI configuration

```yml
name: ci
on:
  push:
    branches:
      - main
      - master
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.x
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force
```

### Step 4: Create a [new branch in your GitHub](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository) project called for example `gh-pages`

### Step 5: Enable the [GitHub pages](https://pages.github.com) on your project and select the branch `gh-pages` as source for your documentation









