# Project: OnBoardCpp

This repo is a collection of training material for C++ developers and general tips about code development.

All pages are managed using MkDocs, see official [documentation](https://www.mkdocs.org) for further details.

An introduction to markdown syntax is available [here](https://www.markdownguide.org).

## Workflow

Install Python and MkDocs.  
For Linux (Debian) users run the following commands:

```
$ sudo apt install python3
$ python3 --version
$ sudo apt install python3-pip
$ pip3 --version
$ sudo apt-get install mkdocs
```

Then follow the steps:

1. Clone the repository

2. Edit pages inside folder: _docs/_

3. Verify the changes locally (http://127.0.0.1:8000) run command  
   ``$ mkdocs serve``

4. upload the changes to remote site (on GitHub branch named _gh-pages_) run command  
   ``$ mkdocs gh-deploy``

5. Open the [website](https://lisr-pcx.github.io/on-board-cpp)

