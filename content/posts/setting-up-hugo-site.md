+++
date = '2025-03-14T14:23:10-04:00'
draft = false
title = 'Setting_up_hugo_site'
+++

## Setting up Hugo Site with PaperMod theme 

### Hugo Site Generate is quick, performant and easier to manage and maintain. I was able to setup everything in no time. I hope this will also help you

**Reference Link:**
https://gohugo.io/getting-started/quick-start/
https://www.youtube.com/watch?v=6BLFYo1wc0Q&t=133s
https://github.com/robamu/my-website.git
My Code: https://github.com/Stratagem360AI/AIGenesis.git
https://blog.desigeek.com/about/

***Steps at a high-level***
- Create a site
- Add content
- Configure the site
- Publish the site

***Prerequisite***
- Install Hugo
> brew install hugo
    - Note: if you do not have brew package. Link: https://brew.sh (install this first and then above command)
- Install Git 
    - Link: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

***Site Creation***
- Create a new site
> hugo new site quickstart
> cd quickstart
> git init
> git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
> echo "theme = 'ananke'" >> hugo.toml
> hugo server
- Note for PaperMod theme follow the instructions here
Link: https://themes.gohugo.io/themes/hugo-papermod/
Demo site: https://adityatelange.github.io/hugo-PaperMod/
> git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
> git submodule update --init --recursive # needed when you reclone your repo (submodules may not get cloned automatically)
- Note the Hugo directory structure comes with a default config file "hugo.toml" However, most of the examples to customize sites are with YAML file. 
- Create a config.yml file and use that as an arguement when building the server
> hugo --config config.yml
- Add the theme to config.yml
> theme: ["PaperMod"]
- Next is customization. Easy hack is to copy over the files in /themes/PaperMod/layouts and its subdirectory to your Hugo layout directories

***Committing changes to GIT***
- Create a GIT repository
- initialize the branch, setup remote origin, and add all the project to the branch
- commit all changes
- push them to the branch

***Publishing the site***
- Note: I used GIT Pages to publish my website so it is accessible through internet. Instead of using GIT Actions, I used GIT Pages with default branch and docs folder setting.
    - build your site without the public folder. Use docs so it matches the GIT Pages setting
    > hugo --minify --destination docs --config config.yml
    - This is eliminate the dependency of public folder
    - commit and push changes again
- Changes on GIT Repo Settings
    - Goto Pages
    - Under Build & Deployment -> Source = Deploy from Branch
    - select branch folder to match your Hugo site branch where you pushed your changes. In many cases, this will be main
    - select the docs folder
- Once the project is build by GIT, the GIT Page should be published and available to view.
