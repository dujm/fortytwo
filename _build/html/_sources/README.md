# fortytwo

## Setup
### Create a conda environment (named as `fortytwo`)
```sh
conda create -n fortytwo python=3.11 

# Activate env
conda activate fortytwo

# Install packages
pip3 install -r requirements.txt

# install jupyter lab and add kernel 
conda install -c conda-forge jupyterlab

# add kernel in jupyter lab
ipython kernel install --user --name=fortytwo
```

### Create a jupyter book
[Build your book](https://jupyterbook.org/en/stable/start/build.html)
```sh
# create a jupyter book in `docs/` (just to make things look more organized)
jupyter-book create fortytwo

# enter main directory
cd fortytwo
```
 * add markdown files in `docs/`

 * update `_toc.yml` file according to md file names

 * update `_config.yml` repository url to `https://github.com/dujjm/dujjm.github.io`


## Deploy a book 
### Create a repo ob github `fortytwo`

### Connect with github
```bash
# build book 
jupyter-book build --all ./

git init 
git remote add origin git@github.com:dujm/fortytwo.git
git add .
git commit -m "initial commit"
git push --set-upstream origin master
```

### Page access 
 * [Jupyterbook on Github](https://jupyterbook.org/en/stable/publish/gh-pages.html)

```bash
pip install ghp-import

# import 
ghp-import -n -p -f -o docs/_build/html
``` 
 * Go to `https://github.com/dujm/fortytwo/settings/pages`
  * Source: `Deploy from a branch`
  * Branch: `gh-pages/docs`
  * Click save 

 * wait 1-2 min 
 * go to `https://dujjm.github.io`

### Save pip requirements
```bash
pip3 freeze > requirements.txt
```

```bash
# generate toc
# new version of jupyter-book
# jupyter-book toc from-project ~/Documents/path  -f jb-book > _toc.yml
 ```