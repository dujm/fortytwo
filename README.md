# fortytwo


## Setup
### 1. Locally: create a conda environment (named as `fortytwo`)
```sh
# create an env
conda create -n fortytwo python=3.11 

# activate env
conda activate fortytwo

# install packages
pip3 install -r requirements.txt

# optional: install jupyter lab and add kernel 
conda install -c conda-forge jupyterlab

# optional: add kernel in jupyter lab
ipython kernel install --user --name=fortytwo
```

### 2. Locally: create a jupyter book repo (also named as `fortytwo`)

```sh
# create a jupyter book
jupyter-book create fortytwo

# enter main directory
cd fortytwo
```
 * Add markdown files in `docs/` (just to make it more organized)

 * Update `_toc.yml` file according to markdown file names

 * Update `_config.yml` repository url (`https://github.com/yourname/fortytwo`)


### 3. Remote: on your Github (`yourname`), create a repo (`fortytwo`) 

### 4. Locally: deploy to Github Page (`https://github.com/yourname/fortytwo`)
 * Connect to Github 
```bash
# build book 
jupyter-book build --all ./

# push to Github
git init 
git remote add origin git@github.com:yourname/fortytwo.git
git add .
git commit -m "initial commit"
git push --set-upstream origin master
```

* Import documents to Github Page 
```bash
pip install ghp-import

# use ghp-import to import documents to Github Page 
ghp-import -n -p -f -o _build/html
``` 

### 5. Remote: configure a publishing source on your Github 
 * Go to `https://github.com/yourname/fortytwo/settings/pages`
 * Source: `Deploy from a branch`
 * Branch: `gh-pages/root`
 * Click save 
 * Wait 1-2 min 
 * Go to `yourname.github.io/fortytwo`



---

## Ref
 * [Build your book](https://jupyterbook.org/en/stable/start/build.html)
 * [Jupyterbook on Github](https://jupyterbook.org/en/stable/publish/gh-pages.html)
 * [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
