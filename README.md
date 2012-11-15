This is a build of ffmpeg made with [vulcan](https://github.com/heroku/vulcan) on the Heroku environment.

### Instructions

* Clone this repository.
* Vendor it into your app. If it's a Rails app, cp it to `vendor`. Commit the changes.
* Apply these configuration settings to your heroku app (making sure to preserve any other PATH changes you've made):
  `heroku config:set PATH=bin:vendor/ffmpeg/bin:vendor/bundle/ruby/1.9.1/bin:/usr/local/bin:/usr/bin:/bin -a yourapp`
  `heroku config:set LD_LIBRARY_PATH=vendor/ffmpeg/lib:/usr/local/lib -a yourapp`

### A word of caution

This repository is large due to library dependencies. The footprint ffmpeg will have on your dyno is large also.

I'm interested into how to reduce this size, but in lieu of that a practical solution
might be to have an ffmpeg-only app and pass it messages from your existing app.

### Credits

This [gist](https://gist.github.com/3963576) from @coopermaruyama. You can use this gist to build a custom copy.

[Using Vulcan to Build Binary Application Dependencies for Heroku](http://www.ryandaigle.com/a/using-vulcan-to-build-binary-dependencies-on-heroku) by @rwdaigle.

