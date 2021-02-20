# `s` <font size="2">(shorthand... for 'shortener')</font>
**A URL shortener powered by GitHub!**

## How to use this service
1. Fork this repository in to your GitHub account, preferably with a short name
2. Go to your newly forked repo's settings and turn on `GitHub Pages`. Set the source branch to `gh-pages`
3. Clone your fork on to your machine
4. To shorten a URL, run
```
./shorten http://your-favourite.com/long-page-name.html [optional-alias]
```

**Pro-tip**: add your cloned working directory to your `$PATH`, then you can run `shorten` from anywhere!

## How it works
The `shorten` script will encode the long URL into a commit message in your repository.
The `sha` of the commit will be used as the shortened URL hash. After the commit has been
written, the script will checkout the `gh-pages` branch and create an HTML file named
{sha}.html, containing a meta tag that will trigger a redirect. That html file is then
committed, and all changes are pushed up to GitHub.

GitHub will then update your repository's static pages, and the html file will shortly
be available at `<username>.github.io/s/<sha>`.