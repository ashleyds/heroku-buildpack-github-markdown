<<<<<<< HEAD
# GitHub Markdown Buildpack

This [Heroku buildpack](https://github.com/rwdaigle/heroku-buildpack-github-markdown) allows you to deploy raw markdown file(s) which will get rendered with GitHub's Markdown parser and served via a simple web server. See this project's [README rendered here](http://afternoon-peak-2333.herokuapp.com/README.html).

It has no code dependencies. Markdown rendering is accomplished using command line utilities and [GitHub's markdown API](http://developer.github.com/v3/markdown/). Serving of the rendered HTML files uses a simple Python web server, available by default on a Heroku dyno.

This buildpack focuses on quick compile times and minimal setup. It is a useful tool for:

* Sharing git-based markdown content rendered with custom CSS
* Ensuring complete compatability with GitHub flavored markdown
* A simple blog/draft mechansim for articles

## Using

In the (git-enabled) directory where your article(s) exist, run the following:

```bash
$ heroku create -b git://github.com/rwdaigle/heroku-buildpack-github-markdown.git
$ git push heroku master
$ heroku open
```

If your markdown file was named `index.md`, you should now see it rendered and styled. Otherwise you will see a directory listing of your files with all `*.md` content now in rendered HTML.

## Updates

As you update your content, deploying and rendering it is as easy as committing your changes to git and doing a `git push heroku master`:

```bash
$ git commit -m "Update article"
$ git push heroku master
```

## Stylesheet

By default the stylesheet used is located at: https://gist.github.com/4579178. If you want to use a custom stylesheet you will need to set a config var on the Heroku app and use a Heroku labs feature so the var will be available at build time.

```bash
$ heroku labs:enable user-env-compile
$ heroku config:set STYLESHEET_URL=https://gist.github.com/raw/4570328/styles.css
```

Because the stylesheet location is embedded at build-time you will need to force a rebuild if you want to change the stylesheet:

```bash
$ git commit --allow-empty -m "Force rebuild"
$ git push heroku master
```

## Notes

While this buildpack is completely functional it is mostly a proof of concept. Please send any interesting derivatives to [@rwdaigle](https://twitter.com/rwdaigle).
=======
# heroku-buildpack-github-markdown
playing based on https://github.com/rwdaigle/heroku-buildpack-github-markdown 
>>>>>>> 9ff6a3ca0757532fcf4a3e78ae4830a8cb525964
