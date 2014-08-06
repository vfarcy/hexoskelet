
My blog at blog dot farcy dot me
============================

This repository holds my blog which you can visit at blog.farcy.me.

The core module, a static website generator developed w/ nodejs is hexo.io. The sources of the blog pages are markdown documents. The pages are stored in the `source` directory (within the master branch). At the compilation phase, html documents are generated and stored within the gh-pages/ branch.

First, you have to install it : `npm install hexo -g`.
 
Then, enter `npm install` at the prompt to install the  packages required by hexo.

Don't forget to modify the `_config.yml` which is a configuration file. You have to adapt it so it suits to your needs. 

The blog is compiled by `hexo generate` and deployed on GitHub by entering `hexo deploy`. 





