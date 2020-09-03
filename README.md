# 1M Gsapper Template

_This Template is currently based on sapper#rollup template._
The default Svelte/[Sapper](https://github.com/sveltejs/sapper) template, available for Rollup and webpack.

This is a work in progress not for production use.

❗ Important to use gsap you must sign up @ [GreenSock](https://greensock.com/docs/v3/Installation) and download zip, then extract gsap-bonus.tgz to /scripts/ folder. ❗

## Getting started with Gsapper

💚💚 Gsap and Sapper Template 🧦🧦

Adding more as I test. Full ReadMe coming soon.

\*\*Not all bonus plugins are free, to use any premium plugins you must purchase the correct membership from [GreenSock Club](https://greensock.com/club/).

## Svelte Components

I am working on creating Svelte components for easy use of different gsap features.

## Gsap as action

Actions in Svelte are a great way to use third party libs. Start with use:animate

### gh-pages deploy

_you can also use gh-pages lib but must configure_

```
# for use with master branch github pages
npm run deploy
```

First create a develop branch and github repo (you can name it anything)
rename the `< >` 's with your info.

```
git init
git branch <your-branch-name>
git checkout <your-branch-name>
```

Then commit and and set origin

```
git add .
git commit -m "a commit message"
git remote add origin https://github.com/<your-git>/<repo-name>.git
git push -u origin <your-branch-name>
```

Finally configure your `/scripts/edit_deploy.js` and rename to `deploy.js`

### Included

svelte-preprocess (postcss,pug,scss)
gh-pages (will include guide for us all files are included)
fa-svelte for Font Awesome5 cause well its awesome
