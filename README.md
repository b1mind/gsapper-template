# 1M Gsapper Template

💚💚 Gsap-Sapper Template 🧦🧦
_based on Svelte/[Sapper](https://github.com/sveltejs/sapper) template._<br>
This is a work in progress not for production use.

### Whats Inside?

- [svelte-preprocess](https://github.com/sveltejs/svelte-preprocess)
- [svelte-fa](https://github.com/Cweili/svelte-fa)
- [gh-pages](https://cweili.github.io/svelte-fa/)

## Getting started with Gsapper

`npx degit "b1m1nd/gsapper-template#develop" <app-name>`

❗ Important to use gsap you must sign up @ [GreenSock](https://greensock.com/docs/v3/Installation) and download zip❗
_\*\*To use any premium plugins you must purchase the correct membership from [GreenSock Club](https://greensock.com/club/)._

Extract gsap-bonus.tgz to /scripts/ folder and install dependencies.
`npm -i`

### Svelte Components

I am working on creating Svelte components for easy use of different gsap features.

### Gsap as action

Actions in Svelte are a great way to use third party libs. Start with use:animate

# Extras

Added libs to enhance production.

### Deploy GitHub Pages

_this uses gh-pages but must configure first_

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

### Using Font Awesome

```html
<script>
  import Fa from 'svelte-fa'
  import { faUser } from '@fortawesome/free-solid-svg-icons'
  const optionsFa = {
    flip: 'horizontal',
    pull: 'left',
    size: '1x',
    color: '#ff0000',
  }
</script>
<Fa icon="{faUser}" style="background: skyblue" {...optionsFa} />
```
