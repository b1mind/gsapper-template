# 1M Gsapper Template

‼ Important to use gsap.ScrollTrigger you must sign up and download zip for bonus.plugins. ‼

_This Template is currently based on sapper#rollup template._
The default [Sapper](https://github.com/sveltejs/sapper) template, available for Rollup and webpack.

## Getting started with Gsapper

💚💚 Sapper Template with Gsap's ScrollTrigger 🧦🧦

Adding more as I test. Full ReadMe coming soon.

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
