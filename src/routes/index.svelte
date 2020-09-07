<script>
  import { afterUpdate, onMount } from 'svelte'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  import { gsap } from 'gsap'
  import MyTrigger from '../components/MyTrigger.svelte'

  import Fa from 'svelte-fa'
  import { faUser, faFlag } from '@fortawesome/free-solid-svg-icons'
  // const themeFa = {
  //   size: '3x',
  //   secondaryOpacity: 1,
  //   primaryColor: '#0438a1',
  //   secondaryColor: '#6c6c6c',
  // }

  let tl = gsap.timeline({})
  function setTimelines() {
    tl.to('.pinned', { background: 'blue' })
      .to('.someText', { x: 200, color: 'yellow' })
      .to('.pinned', { background: 'green' })
  }

  onMount(() => {
    setTimelines()
  })

  afterUpdate(() => {
    ScrollTrigger.refresh()
  })
</script>

<svelte:head>
  <title>gSapper template</title>
</svelte:head>

<!-- prettier-ignore -->
<template lang="pug">
	h1 this is a pug header
</template>

<figure>
  <img alt="Success Kid" src="successkid.jpg" />
  <figcaption>Have fun with Sapper!</figcaption>
</figure>

<div class="test">
  <MyTrigger
    stClass="pinned"
    {tl}
    stOptions={{ pin: true, scrub: true, start: 'top 200', end: '300 top', toggleActions: 'play reverse play reverse' }}
  >
    <div class="someText">Some timeline</div>
  </MyTrigger>
</div>

<div class="spacer" />

<MyTrigger
  stClass="test"
  stOptions={{ pin: true, scrub: true, start: 'center center', end: '300 top' }}
  tween={{ autoAlpha: 0, x: 100, stagger: 0.5 }}
>
  <Fa icon={faFlag} />
  <Fa icon={faFlag} />
  <Fa icon={faUser} />
  <Fa icon={faFlag} />
  <Fa icon={faFlag} />
</MyTrigger>

<MyTrigger
  stClass="suk"
  stOptions={{ pin: true, scrub: true, start: 'center center', end: '300 top' }}
  tween={{ autoAlpha: 0, y: 100, stagger: 0.5 }}
  tweenType={'to'}
>
  <p>one</p>
  <p>two</p>
  <p>three</p>
  <p>four</p>
  <p>five</p>
  <p>six</p>
</MyTrigger>

<div class="spacer" />

<style lang="scss">
  h1,
  figure {
    text-align: center;
    margin: 0 auto;
  }

  .test {
    padding: 10px;
    background: burlywood;
  }

  .spacer {
    min-height: 700px;
    margin: 1rem 0;
    background: lightblue;
    text-align: center;
  }

  h1 {
    font-size: 2.8em;
    text-transform: uppercase;
    font-weight: 700;
    margin: 0 0 0.5em 0;
  }

  figure {
    margin: 0 0 1em 0;
  }

  img {
    width: 100%;
    height: 250px;
    max-width: 400px;
    margin: 0 0 1em 0;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 4em;
    }
  }
</style>
