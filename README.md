# ShortHub ⚡️ <font size=3>GitHub Pages Powered URL Shortener</font>

## What
Run your own personal URL shortener for free, powered by GitHub Pages!

## Installation
1. Fork this repository
2. *Optional:* Rename your fork to something succinct, preferrably one letter (e.g. `s`)
3. Go to your newly forked repo's settings and turn on `GitHub Pages`. Set the source branch to `redirects`
4. Clone the fork on to your machine

**⚡️ Pro-tip 1**: Add your cloned working directory to your `$PATH`, then you can run `shorten` from anywhere!

**⚡️ Pro-tip 2**: Jazz it up 🎷 [Register a custom domain name](https://hover.evyy.net/gbPJJO) and then [point it at your GitHub Pages site](https://docs.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site).

## Usage
To shorten a URL, run
```bash
./shorten http://your-favourite.com/long-page-name.html [optional-alias]
```

## How?
The `shorten` script will encode the long URL into a commit message in the `redirects`
branch of your repository. The `sha` of the commit will be used as the shortened URL hash.
After the commit has been written, the script will create an HTML file named `{sha}.html`,
containing a meta tag that will trigger a redirect. The html file is then committed, and
all changes are pushed up to GitHub.

GitHub will then update your repository's static pages, and the html file will shortly
be available at `<username>.github.io/s/<sha>`.

## FAQ
### Q: Why doesn't the shortened link doesn't immediately?
**A**: GitHub needs to re-deploy your static pages to github.io - this is very fast, but
not quite instant. Once you've created a shortened url with `shorten`, you may need to wait
~15-20s for the link to become active.


## Why?
¯\_(ツ)_/¯