<script>
  import MyTrigger from '../components/MyTrigger.svelte'
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<h1>About this site</h1>
<div class="spacer" />
<p>This is the 'about' page. There's not much here.</p>
<div class="spacer" />

<!-- prettier-ignore -->
<MyTrigger 
	stOptions={{ pin: true, scrub: false, start: 'center center', end: '300 top' }} 
	tween={{ autoAlpha: 0, y: 100, stagger: 0.5 }}>
  <span>one</span>
  <span>two</span>
  <span>three</span>
  <span>four</span>
  <span>five</span>
  <span>six</span>
</MyTrigger>
<div class="spacer" />

<style lang="scss">
  .spacer {
    min-height: 700px;
    margin: 1rem 0;
    background: lightblue;
    text-align: center;
  }
</style>
