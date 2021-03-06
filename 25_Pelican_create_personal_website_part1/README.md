This is the personal website generated by [Pelican](https://github.com/getpelican/pelican) based on [Qingkai's Tutorial part 1](http://qingkaikong.blogspot.com/2016/07/create-personal-website-with-pelican.html). 

Markdown file are created using the editor https://stackedit.io/editor#

Recently, I need create a personal website to advertise myself (I am about to graduate next year, so a personal website seems a must have to find a job ^)^). After a simple search, I found [pelican](http://blog.getpelican.com/), a python tool that allow you to create the website in a few steps! I immediately decided to create  a website using it. 

There're many blogs showing how to install pelican, so I will skip it.  To make things simple, I will use the site I created as an example. You can see my website [here](http://seismo.berkeley.edu/qingkaikong/). We will create a similar style site in the next steps.

Let's start after you installed Pelican, and the Markdown extension, see [here](http://docs.getpelican.com/en/3.6.3/install.html) if you don't know how to install, or you can check out this [blog](http://duncanlock.net/blog/2013/05/17/how-i-built-this-website-using-pelican-part-1-setup/). 

**Step 1:**
Follow the documentation to run the pelican-quickstart to create the website folder.  Most of the questions you can use default options, and your own personal information. (I use SSH later to upload my website, so I put my username and ssh host url there). 

**Step 2:** 
A quick understand of the folder structure:  
  yourproject/  
  ├── content  
  │   └── (pages)  
  ├── output  
  ├── develop_server.sh  
  ├── fabfile.py  
  ├── Makefile  
  ├── pelicanconf.py         
  └── publishconf.py  

* pelicanconf.py  is the general configuration file
* publishconf.py is the configuration file for publishing the site
* fabfile.py is the configuration file for tool [Fabric](http://www.fabfile.org/) that you can automize your develop process later. 
* Makefile is also aimed at automizing the develop process
* content folder will store all the different files you will develop, for our case, markdown files or images we need embed into the site. For example, you can have a pages folder to store all the different pages, and an image folder to store all the images. 
* output folder will have all the files that created for your site, for example, html, css, and so on. 

**Step3:**

You can create folders in the content folder for different purposes. For example, you can create a pages folder to store all the pages, and images folder to store all the images you need. 

After you created the pages folder, you can put the pages you want on your website into this folder. For example, let's put 3 pages into this folder, Home.md, Fun.md, and About.md. Here's the example for the Home.md:

```markdown
Title: Home
Date: 2016-06-10 15:30
URL:
save_as: index.html     

---  
This is my home page!
---

## News and Events:
2016/06/10 I create my home page 
```

I think I don't need to explain this, if you are not familiar with Markdown, checkout this great [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). The only thing you should pay attention to in this page is the URL and save_as, this is telling pelican that we want this page as the default page when someone first entered into our website. You only need this in the home page, for others, you don't need this. 

**Step4:**

Now you can build you website using 'make html', and this will generate the website to the output folder. To see it, first start a server by using the command 'make serve' in the output folder, then you can check the website at 'http://localhost:8000/'. 

You notice that, it all looks good, except the tabs are in reverse order 'About', 'Fun', and 'Home'. To change this, just add PAGE_ORDER_BY = 'date' to your pelicanconf.py file. Now you should see them in the correct order. 

Now you have the website! And in the next blog, we will see how we change theme, add images, videos, attach files, and publish your site!
