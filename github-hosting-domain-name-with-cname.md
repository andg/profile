---
layout: default
title: Github hosting a domain name using a CNAME file by Andrew Gauger
---

[github](https://help.github.com/articles/setting-up-a-custom-domain-with-pages) has a page for setting up domains.  I have a [CNAME file](https://github.com/andg/profile/blob/master/CNAME).

### andrewgauger.com
[Namecheap.com](http://www.namecheap.com) has good security mechanisms in place.  I had lost my administrative email account (since I have been going through email addresses lately) and went through recovery process to regain my domain name and they followed all best practices throughout the process.  I do recommend them for this and renewing my domain was $11.  It had expired and I was able to reactive without surcharges or loosing my domain to poachers.

```
@    204.232.175.78    A
www  andg.github.io    CNAME
```
### email with github support
I had a support email in place that adviced I made sure the following things were correct 
* [header](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter)
* [gh-pages](https://gist.github.com/chrisjacob/833223) should be created with
```bash
git checkout -b gh-pages
git push origin gh-pages
```

### index.md
I created an index.md file with the following sample header:
```
---
layout: default
title: Andrew Gauger
---
```
I committed this to both gh-pages and master to be sure
```bash
git checkout gh-pages
git add index.md
git commit -m "render markdown"
git push origin gh-pages
git checkout master
git merge gh-pages
git push origin master
```
