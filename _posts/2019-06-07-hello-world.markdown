---
layout: post
title:  "Hello World!"
date:   2019-06-07 22:10:17 -0400
categories: blog
tag: how_to, jekyll
---

Hello world! It's the first post on this blog ever! It'll be a recap on how this site was built. 

### Initialization
As per the [Jekyll Quickstart Guide](https://jekyllrb.com/docs/), we'll start off by running: 
```
    gem install jekyll bundler;
    jekyll new blog;
    cd blog;
    bundle exec jekyll serve;
```

Then, navigate over to `http://localhost:4000`, where everything is set up to go.

### Adding a theme
The default jekyll blog uses the `minima` theme. This blog, however, uses the `so-simple-theme` by [mmistakes](https://github.com/mmistakes/so-simple-theme). It comes packed with a ton of features built-in, and looks great, too! 

This requires changes in the `Gemfile`. I commented out lines 11 and 14 by appending the lines with `#`:
```
# gem "jekyll", "~> 3.8.5"
# gem "minima", "~> 2.0"
```

Then, I added the following line: 
```
gem "github-pages", group: :jekyll_plugins
```

Finally, I reloaded the page with: 
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
We need to create a base `.md` file to be picked up. Let's make one more directory and add one more file:
```
    cd blog;
    mkdir docs;
    cd docs;
    touch search.md;
```

Copy [this](https://raw.githubusercontent.com/mmistakes/so-simple-theme/master/docs/search.md) into that file.

Now save and reload, you should now be able to not only see a search page, but use it also!

### Customizing it to fit YOU
This is the easy part. We only need to make changes in one place, really: `_config.yml`. 

See [this](https://github.com/mmistakes/so-simple-theme/blob/master/_config.yml) link to see a ton of possible options you can add.

The only thing left now is to start adding some posts! Just visit `_posts` and start tinkering with the one available. 

### Final thoughts
Posts are all markdown files, so this [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) will come in handy.

