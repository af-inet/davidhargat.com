+++
title = "so I wrote a web server"
date = "2017-03-26T23:21:58-04:00"
tags = ["blogging","c","server"]
+++

---

**UPDATE 2020:**

This post is no longer accurate since I moved my website from Digital Ocean to Github Pages.

(this is actually how I ran my site in 2017 though)

---

## So I wrote a web server...
... and you're using it right now! But wait, what is it exactly?

Well, think of it like an [nginx](https://en.wikipedia.org/wiki/Nginx) of sorts.

I named it [plexer](https://github.com/af-inet/plexer/) because I wanted to experiment with multi[plex](http://pubs.opengroup.org/onlinepubs/9699919799/functions/poll.html#tag_16_363)ing [sockets](https://en.wikipedia.org/wiki/Berkeley_sockets), and it's written in one of my favorite languages, C.

plexer will happily compile on either Linux or Mac. Just run `make` and watch it go!

The current implementation only serves your current directory.

So if you were to compile and run it right now - you'll see an index of the source files, something like this:

![plexer running inside a terminal](/img/about-this-blog.jpg)
 
And that's about it! I have it running on a cheap digital ocean droplet in a folder with a bunch of html (thats all this site is).

There are also some scripts for deploying plexer (packaged with my personal site) on debian. It's set up with a cronjob to poll my github and automatically re-deploy when I push any changes.

In the future I plan to write more posts detailing all the interesting things I've learned (and am still learning) working on plexer.

## Try it yourself:

```
git clone https://github.com/af-inet/plexer
cd plexer
make
./plexer -vp 8080 # verbose, run on port 8080
```

## Security Concerns
Since plexer is strictly a for-fun project and isn't peer-reviewed whatsoever, it should go without saying that you SHOULD NOT use it in production unless you're looking for [some](https://en.wikipedia.org/wiki/Buffer_overflow) [fun](https://en.wikipedia.org/wiki/Arbitrary_code_execution).

(Personally I'm looking forward to the day someone exploits this)

