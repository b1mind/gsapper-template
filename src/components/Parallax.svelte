<script>
  //todo Parallax svelter style
  import { afterUpdate, onMount } from 'svelte'
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  import { refreshTriggers, killTimeline } from '../../gsap.js'

  //set default props for trigger

  function makeParallax() {
    gsap.utils.toArray('section').forEach((section, i) => {
      section.bg = section.querySelector('.bg')

      // Give the backgrounds some random images
      section.bg.style.backgroundImage = `url(https://picsum.photos/${innerWidth}/${innerHeight}?random=${i})`

      // Do the parallax effect on each section
      if (i) {
        section.bg.style.backgroundPosition = `50% ${innerHeight / 2}px`

        gsap.to(section.bg, {
          backgroundPosition: `50% ${-innerHeight / 2}px`,
          ease: 'none',
          scrollTrigger: {
            trigger: section,
            scrub: true,
          },
        })
      }

      // the first image should be positioned against the top. Use px on the animating part to work with GSAP.
      else {
        section.bg.style.backgroundPosition = '50% 0px'

        gsap.to(section.bg, {
          backgroundPosition: `50% ${-innerHeight / 2}px`,
          ease: 'none',
          scrollTrigger: {
            trigger: section,
            start: 'top top',
            end: 'bottom top',
            scrub: true,
          },
        })
      }
    })
  }

  //housekeeping, keeping it svelter
  onMount(() => {
    makeParallax()
    return () => {
      //st.kill()
      // ScrollTrigger.refresh()
    }
  })

  afterUpdate(() => {
    //Todo would like this to control when its added or leaves
    // ScrollTrigger.refresh()
    // console.log(`component trigger added all refreshed`)
  })
</script>

<section>
  <div class="bg" />
  <slot>
    <h1>Simple parallax sections</h1>
  </slot>
</section>

<style type="text/scss">
  section {
    position: relative;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    background-repeat: no-repeat;
  }

  h1 {
    color: white;
    text-shadow: 1px 1px 3px black;
    z-index: 1;
    font-size: 3em;
    font-weight: 400;
  }
</style>
