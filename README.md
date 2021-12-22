[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

# 🔗 Od.dyn

A URL shortener powered by [nlsn.cf's code](https://github.com/nelsontky/gh-pages-url-shortener) & GitHub

## 👨‍🏫 How to use

0. Make sure you're using [OpenNIC](https://opennic.org). If you're not using it, you can check how to start using it [here](https://welcomegeek.github.io/main_page#start-using-opennic).
   - If you have a problem, you can use our alternative domains:
     - [oy.now.sh](https://oy.now.sh)
     - [od-dyn.now.sh](https://od-dyn.now.sh)
     - [oddyn.now.sh](https://oddyn.now.sh)
     - [jaj.now.sh](https://jaj.now.sh)
     - [jajas.now.sh](https://jajas.now.sh)

1. Enter to [od.dyn](http://od.dyn).

2. Add your long URL to the form.

4. Click on "Create issue".

3. The newly created short url can be accessed via `od.dyn/{issue_number}`

- [Demo video](https://youtu.be/9tQqACeBUCM)

## 📄 ToS

You shall not use this service to short URLs with content illegal on the USA and Argentina or that could break [GitHub's ToS](https://docs.github.com/en/github/site-policy/github-terms-of-service) and include on all your submitions' body the following text: `By submiting this URL, I accept Od.dyn's [ToS](https://github.com/luqaska/od.dyn#-tos).`.

## ☕️ Features

1. Unlike many URL shorteners, this one ~~does not need a database~~ uses a
   "database" in the form of GitHub issues and can be entirely hosted on GitHub
   pages.

2. There is no need for the pound symbol - short URLs look clean like this:
   `nlsn.cf/1` instead of looking like this: `nlsn.cf/#1`.

## 💡 How does this work?

_Thanks to @kidGodzilla for the pretty neat explanation
[here](https://github.com/nelsontky/gh-pages-url-shortener/issues/5#issuecomment-728040879)._

> 1. 404.html handles all requests
> 1. Small javascript snippet fetches a JSON representation of the GitHub issue
>    via the JSON API, and redirects to the issue title, as a URL.
> 1. Profit?

## 😎 This is so cool! How can I use this with my own domain?!

_Disclaimer: This method of creating a URL shortener is hacky and not meant to
be reliable. Do proceed at your own risk!_

1. Fork the repo before cloning your fork.
1. Set up GitHub pages for your forked repo.
   1. In your forked repo, **click the Settings tab** and scroll down to the
      GitHub Pages section.
   1. Then select the **main branch** source and click on the **Save** button.
   1. <img src="https://i.imgur.com/kjinFX9.png" alt="How to create GitHub page" height="176px">
1. If you are using your own domain:
   1. [Set your domain up for GitHub pages.](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)
   1. Change the URL in `CNAME` file to your domain.
1. If you are using GitHub page's default domain i.e. Something like
   `https://<username>.github.io/<repo-name>/`
   1. Delete the `CNAME` file.
   1. Change `var PATH_SEGMENTS_TO_SKIP = 0;` at the top of `404.html` to
      `var PATH_SEGMENTS_TO_SKIP = 1;`.
      1. This is as GitHub domains have an additional path segment (the repo
         name) after the host name.
1. Create a new repo as a database. (Or you could use your forked repo)
   1. Update `var GITHUB_ISSUES_LINK = "<your-github-issues-link>";` at the top
      of `404.html` accordingly afterwards.
      1. Format for `GITHUB_ISSUES_LINK`:
         `https://api.github.com/repos/{owner}/{repo}/issues/`
      1. Remember the trailing `/`!
1. Push your changes to your forked repo, and your low cost and cool as heck URL
   shortener will be ready for use!

## 🍴 Featured forks

To feature your fork here, edit this section and open a PR!

- [eexit.github.io/s](https://github.com/eexit/s) - Created a bash script that
  allows for shortening of URLs straight on the command line! Check out his
  script
  [here](https://github.com/nelsontky/gh-pages-url-shortener/issues/49#issue-745134937).
- [gh-short-url](https://github.com/mayandev/gh-short-url) - A npm command line
  tool that uses GitHub pages to convert short URLs.
