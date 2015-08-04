---
layout: post
title:  "Up and Running with Jekyll"
date:   2015-08-04 20:56:37
categories: jekyll update
---

Ever wanted to create static, Markup-driven website that's simple to develop, deploy and maintain? Then Jekyll could be right for you. In this 15 minute introductory tutorial, [Travis Neilson](https://twitter.com/travisneilson?lang=en) from [DevTips](https://www.youtube.com/user/DevTipsForDesigners) explores the basics of this easy-to-use technology and shows how developing a website in Jekyll easy, no frills solution you've been looking for.

<iframe width="560" height="315" src="https://www.youtube.com/embed/iWowJBRMtpc" frameborder="0" allowfullscreen></iframe>

## Introduction (0:13)

For the past few weeks on my channel called [DevTips](https://www.youtube.com/user/DevTipsForDesigners), we've been building a series of videos called [How to Make a Website From Start to Finish](https://www.youtube.com/playlist?list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI). I've been trying to give everybody a "seat at the table" as we've gone through the whole creative prcess, starting with [discovery and ideation](https://www.youtube.com/watch?v=VcMjo_wczCc&index=2&list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI), through [empathy and organization](https://www.youtube.com/watch?v=VcMjo_wczCc&index=2&list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI), to [sketching and wireframes](https://www.youtube.com/watch?v=mkHFrk3WuYQ&index=3&list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI), and, for the last video, [visual design](https://www.youtube.com/watch?v=mkHFrk3WuYQ&index=3&list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI). I've tried to time this particular video for today so that everyone at [PHP Academy](https://www.youtube.com/user/phpacademy) can get the first technical lesson, which I am very excited to share. For today's lesson, you do not need to watch any of those other videos; today stands on its own. But if you do want some more context, [here's a link to the playlist that we've been building](https://www.youtube.com/playlist?list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI).

## Building a single page website with Jekyll (1:04)

Today we are looking at setting up our development environment and building a single page portfolio website, which could be used for a designer or artist or photographer etc.

## The Jekyll Platform (1:18)

It's always important to match the needs of the project with the capabilities of the platform, so for this project I've chosen to use the static site generator called Jekyll. If you are not familiar with [Jekyll](http://jekyllrb.com/) or [similar technologies](https://staticsitegenerators.net/), allow me to explain some of the fundamental principles involved here. In general here's how it works.

1. You make a template
2. You make content
3. You run Jekyll
4. You get a whole site of individual static HTML pages
5. After you get the pages, you can upload them to any server and now you have a website

This is really awesome and exciting for a few reasons.

* **Faster site**: because your server does not need to talk to a database on page request, it's a lot faster.
* **More secure**: because there is no database, your site will be a lot more secure; there's simply no way to hack it.
* **Less maintenance**: also because there's no database, there's fewer parts, fewer things that can go wrong and hence less maintenance
* **Lower cost**: fewer parts to maintain also means there's fewer things to pay for, so Jekyll is also a very cheap way to maintain a website
* **Free hosting on [Github](https://github.com/)**: in fact, Jekyll websites are hosted for free on the fast and reliable Github servers as [Github Pages](https://pages.github.com/)
* **Blog aware via [Markdown](http://daringfireball.net/projects/markdown/)**: finally, Jekyll is blog aware, meaning you can write your content in Markdown, so for bloggers and Markdown enthusiasts, this is awesome.

For more information about the extended uses of Jekyll, I recommend you listen to [episode 54 of The Web Ahead 5by5 podcast](http://5by5.tv/webahead/54), where Jen Simmons discusses the topic with [Young Hahn](https://twitter.com/younghahn) and [Dave Cole](https://twitter.com/dhcole), who [successfully used Jekyll to power the American President Barack Obama' campaign website](http://kylerush.net/blog/meet-the-obama-campaigns-250-million-fundraising-platform/) last term. 

## Getting Started (3:10)

Jekyll is a Ruby app that you install on your system. On Jekyll's website there's some really [fast and easy instructions on how to get started](http://jekyllrb.com/docs/home/). So we are going to follow them and get up and running.

The first thing we need to do is [install Jekyll](http://jekyllrb.com/docs/installation/).

```
$ sudo gem install jekyll
```

Now that Jekyll is installed, we can just check to make sure it's installed up to the latest version, which should be ???? as of ????

```
$ jekyll -v
```

The next step is to start a new Jekyll project. To do this, we `cd` to to directory we want to create the project in, and run `jekyll new` followed by the name of the project you want to create. I'll create my project in my `Desktop` folder.

```
$ cd Desktop
$ jekyll new portfolio
```

Now a project directory called `portfolio` has been created on the `Desktop`. 

So we now `cd` into the `portfolio` directory. Once we are inside of the `portfolio` folder, I upload the project to my local server by typing the following:

```
$ jekyll serve
```

By doing this Jekyll compiles all the files in the `portfolio` folder into a workable site structure. And it also sets up a server that will run on Port 4000. So if we go to our browser and type `localhost:4000` we should see our Jekyll site up and running using the Jekyll theme, which is quite nice. There are also [tons of nice, free Jekyll themes](http://jekyllthemes.org/) out there that you can use.

## Jekyll tour (5:11)

Now that we have our Jekyll site up and running, the work is nearly done, but let's take a tour of our Jekyll project so we can get familiar with how it works and how it's organized.

So open up your newly created Jekyll project in your favorite code editor and we can start to explore it. Your high level [directory structure](http://jekyllrb.com/docs/structure/) should look like this.

```
- _includes  <br>
- _layouts  
- _posts  
- _site  
- _config.yml  
- _about.md  
- _feed.xml  
- _index.html
```

## Configuration (5:29)

The first, and probably the most important, file in the Jekyll directory structure is `_config.yml`. This is where your settings live, including things like the title, email, description, etc. You can also add settings yourself. For instance, if you want to tell Jekyll wehre you want your server to be you can add the following to the `_config.yml` file: 

```
...  
port: 8080
```

Then you can quit your server by typing `Ctrl-C`, restart it using `jekyll server`, and your Jekyll project should be running on port 8080. You can check this by typing `localhost:8080` into your browser.

You can check out info on all the configuration settings at [Jekyll docs](http://jekyllrb.com/docs/configuration/), which has extensive and easy-to-understand documentation on all things Jekyll.

## The `_site` folder (6:57)

After you've looked at the configuration file, there's a lot of important folder structures to understand. Let's start with the `_site` folder.

The `_site` folder is one of the more important ones, and it will be automatically generated by Jekyll. This is not something you need to manipulate yourself. In fact, you should not touch it. Because what happens is when Jekyll runs, it will take all the content - i.e. your pages, your templates, your includes, your posts - and it will render them and stick them inside of the `_site` folder. So the `_site` folder is a rendered version of all of your pages, and inside the folder a directory structure is created that will mirror the structure of your url.

The html files inside the lowest level folders, in this case the `index.html` file, are fully rendered HTML pages, they are not the template talking to the server on the page request.

All of this happens when Jekyll is running, and not only does it create these pages but it also moves all of your assets (images, javascript, css) into the `_site` folder. So you don't have to touch the `_site` folder, but you should understand that the `_site` folder is the final output of Jekyll's work.

## The `_layouts` folder (8:34)

The `_layouts` folder is another important one, which includes your main templates. 

The `default.html` template includes your main structure and a `div` for the main content to be inserted into.

When you get into specifics, the `post.html` template makes allotments for aspects such as the page title, the publishing date, and the post content.

This specific `post.html` template is in contrast to the `default.html` template, which simply spits out all content into the `{{ content }}` placeholder as seen above.

## The `_includes` folder (9:12)

In the `_includes` folder's layout templates you'll notice they are using a bunch of `include` statements, so if you want to write nice, modular code, then you would put your `include`s into the `_includes` folder. This folder has has modularized sections of your html code such as the `footer`, `header`, and `head`. So you don't have to write your code twice, and it's just already there in the templates and you can include it into all of your files.

## The `_posts` folder (9:35)

Individual blog entries will all be contained in the `_posts` folder. Files in this folder follow the pattern `Date.Title.markdown`, which in practice would look something like this: `2015-08-04-welcome-to-jekyll.markdown`. And then when Jekyll is run, it will put it in the right directory in the `_site` folder as we previously discussed. So all of your posts will fill up the `_posts` folder as Markdown documents and Jekyll will process them and put them in the correct file structure in the `_site` folder, where they will be ready to be served as fully rendered HTML pages.

You can use the `_config.yml` document to determine if you want your permalinks by date or by name or by category. There are a lot of different options there, and it's all very clean and organized.

## Front Matter (10:20)

At the top of every content page (though not necessarily layouts and templates) there will be a block of text that looks like this:

```
layout: post  
title: "Welcome to Jekyll!"    
date: 2015-08-04 18:44:33  
categories: jekyll update  
```

This is called [Front Matter](http://jekyllrb.com/docs/frontmatter/). It's very powerful when it comes to the templating engine that is Jekyll. There are a few standard items such as `date` and `title`, but they can be called anything and then used anywhere in the template. I'll often create a special class name that I'll stick into the `body` tag of the page like so:

```
...  
categories: jekyll update  
body-class: post-welcome  
```

So that way when I'm writing a post or a page, there's a special class hook in the `body` tag in case I need to do some special styling for that specific post or page.

In the above example, the Front Matter `title` variable is assigned "Welcome to Jekyll!", and when we look at the `post.html` template, it's called using `page.title`.

 Elsewhere in this template, we can see that the `page` variable is involved in logic within a `p` element, which says "if there's a date, print a date" and "if there's an author, print the author's name". You can nest your logic into this whole block.

```
{{ page.date | date: "%b %-d, %Y" }}{% if page.author %} • {{ page.author }}{% endif %}{% if page.meta %} • {{ page.meta }}{% endif %}
```

You can make these YAML variables anything you want. They can even include HTML markup, so you can start inserting HTML into different pages dynamically based on the content of the post or page. That can be really convenient, and you can get very clever with that.

## SASS and Jekyll (12:25)

New to Jekyll 2 is the ability to compile [SASS](http://sass-lang.com/), so let me show you how to get that running.

Go to the `css` folder, and change the `main.css` file into a SASS file by changing the name to `main.scss`. Then, in the top of your SASS file put a YAML header (two lines of `---`), which doesn't actually need to be full of anything.

Then save the file, and restart Jekyll by quitting it (`Ctrl-C`) and starting it up again (`jekyll serve`). Or you can avoid having to quit and restart everytime you change files by adding `--watch` to the Jekyll command line `serve` command. This watches the Jekyll code, and if there are any changes, it will output a new version of Jekyll.

```
$ jekyll serve --watch
```

Now inside the `_site` folder, I'll have my `main.css` file with the compiled SASS code, so there is no need to run your SASS code in the terminal in parellel with Jekyll. Jekyll also does [Coffeescript](http://coffeescript.org/) if you are into that.

## Next steps and follow up resources (13:52)

That's it for our tour of the Jekyll site generator. Hope you enjoyed that. Next week we will jump into using Jekyll and developing the project that we've been working on for the past two or three weeks over on DevTips. For more about the project that we set up for today, take a look at the [playlist](https://www.youtube.com/playlist?list=PLqGj3iMvMa4KQZUkRjfwMmTq_f1fbxerI&feature=iv&src_vid=iWowJBRMtpc&annotation_id=annotation_731376265) for all the videos we've created up to this point. After we complete the project, I'll be giving away the site for free to use for yourself so keep on peeking back on DevTips and checking out the progress there. Also, if you want to hear me talk a little more about Jekyll, a while ago I did a collaboration with my friend Jon, who hates Jekyll. [So I recently visited Jon and talked with him about Jekyll](https://www.youtube.com/watch?v=u22CLlw4_hg&feature=iv&src_vid=iWowJBRMtpc&annotation_id=annotation_3493536781) to see if I could help him to be converted over to the House of the Jekyll Lovers. 

Thanks so much for watching the video! And a big thank you and much respect goes to Alex at PHP Academy who keeps on letting me post these videos here. Thanks so much!


