---
layout: page
title: Jekyll Local Testing In XP
---

### 1. Software ###

- Ruby: [rubyinstaller-1.9.3-p125](https://dl.bintray.com/oneclick/rubyinstaller/rubyinstaller-1.9.3-p125.exe)
- DevKit: [DevKit-tdm-32-4.5.1-20101214-1400-sfx](https://dl.bintray.com/oneclick/rubyinstaller/DevKit-tdm-32-4.5.1-20101214-1400-sfx.exe)
- Jekyll  Version(1.1.2)

### 2.Install ###
- Ruby: *Add PATH*
- DevKit:
	- `cd DevKit` 
	- `ruby dk.rb init`
	- `ruby dk.rb install`
- Jekyll：
	- `gem install jekyll -v "1.1.2"`
	- `jekyll -v` display version 1.1.2 
    - Issue
	    - Liquid error: incompatible character encodings: UTF-8 and GBK
        
        - Fix:File: ***jekyll-1.1.2\lib\jekyll\convertible.rb***

        > **change**
        >  *self.content = File.read(File.join(base, name))*
        >  **as** 
        >  *self.content = File.read(File.join(base, name),:encoding=>"utf-8")*
        
### Testing ###
- `jekyll new blog`
- `cd blog`
- `jekyll build`
- `jekyll server`
- `view website:`[http://localhost:4000/](http://localhost:4000/)


