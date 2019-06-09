---
layout: post
title:  "Hello World!"
date:   2019-06-07 22:10:17 -0400
categories: blog
tag: [how_to, jekyll]
author: taimorekhan
---

Hello world! This is my first blog post ever! It'll be a recap on how this site was built. 

### Initialization
As per the [Jekyll Quickstart Guide](https://jekyllrb.com/docs/), start off by running: 
```
    gem install jekyll bundler;
    jekyll new blog;
    cd blog;
    bundle exec jekyll serve;
```

Then, navigate to `http://localhost:4000`, where everything is set up to go.

### Adding a theme
The default jekyll blog uses the `minima` theme. This blog, however, uses the `so-simple-theme` by [mmistakes](https://github.com/mmistakes/so-simple-theme). It comes packed with a ton of features built-in, and looks great, too! 

This requires changes in the `Gemfile`. Comment out lines 11 and 14 by appending the lines with `#`:
```
# gem "jekyll", "~> 3.8.5"
# gem "minima", "~> 2.0"
```

Then, add the following lines: 
```
gem "jekyll-theme-so-simple"
gem "github-pages", group: :jekyll_plugins
```

Control-C, then reload the page with: 
```
bundle exec jekyll serve
```
And, voila! The theme should be applied next time you visit `http://localhost:4000`!

### Navigation bar
Where's the nifty nav bar at the top? Well, it will require a few changes before it shows up. 

All it takes is one new directory and one configuration file: 
```
    cd blog;
    mkdir _data;
    cd _data;
    touch navigation.yml;
```

[Here's](https://github.com/mmistakes/so-simple-theme/blob/master/_data/navigation.yml) an example of some of the available options.

By uncommenting at least one of the sections, the nav bar should be visible at the top.

Clicking on the section reveals a 404 page though, what gives?

### Seeing the pages
There needs to be a base `.md` file to be picked up. Make one more directory and add one more file:
```
    cd blog;
    mkdir docs;
    cd docs;
    touch search.md;
```

Copy [this](https://raw.githubusercontent.com/mmistakes/so-simple-theme/master/docs/search.md) into that file.

Now save and reload, there should now be a fully functional search page!

### Customizing it to fit YOU
This is the easy part. There only needs to be changes in one place, really: `_config.yml`. 

See [this](https://github.com/mmistakes/so-simple-theme/blob/master/_config.yml) link to see a ton of possible options you can add.

Line 16 actually caused an error with Github Pages later, so get rid of it:

~~`theme: jekyll-theme-so-simple`~~

In order to deploy to Github pages, uncomment line 17 to only use remote-theme:

`remote_theme: mmistakes/so-simple-theme`

Click [here](https://github.com/tk3413/tk3413.github.io/blob/master/_config.yml) to see what else I changed up in mine

Now to start adding some posts! Just visit the `_posts` directory and start tinkering with the one available. 

### Traffic control
On Github, add in a [CNAME](https://github.com/tk3413/tk3413.github.io/pull/2/files) file with your CNAME info.

Then, purchase a domain through [Google Domains](https://domains.google/#/) and set it up with the following configurations: 

![domain-info](/assets/images/google-domain-info.png)

The first two point to Github's servers, and the last points specifically to the page. 

And voila! Navigating to the CNAME should point to Github pages. 

### Final thoughts
Posts are all markdown files, so this [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) will come in handy.

For more help with traffic, checkout this [post](http://www.curtismlarson.com/blog/2015/04/12/github-pages-google-domains/), it was a huge help.

Here is the [code](https://github.com/tk3413/tk3413.github.io) for this site.