<script lang="ts">
  import { onMount } from 'svelte'
  const wave1: string =
    'M0,160L30,154.7C60,149,120,139,180,122.7C240,107,300,85,360,85.3C420,85,480,107,540,96C600,85,660,43,720,37.3C780,32,840,64,900,64C960,64,1020,32,1080,69.3C1140,107,1200,213,1260,213.3C1320,213,1380,107,1410,53.3L1440,0L1440,0L1410,0C1380,0,1320,0,1260,0C1200,0,1140,0,1080,0C1020,0,960,0,900,0C840,0,780,0,720,0C660,0,600,0,540,0C480,0,420,0,360,0C300,0,240,0,180,0C120,0,60,0,30,0L0,0Z'
  const wave2: string =
    'M0,0L30,42.7C60,85,120,171,180,197.3C240,224,300,192,360,154.7C420,117,480,75,540,53.3C600,32,660,32,720,42.7C780,53,840,75,900,69.3C960,64,1020,32,1080,37.3C1140,43,1200,85,1260,133.3C1320,181,1380,235,1410,261.3L1440,288L1440,0L1410,0C1380,0,1320,0,1260,0C1200,0,1140,0,1080,0C1020,0,960,0,900,0C840,0,780,0,720,0C660,0,600,0,540,0C480,0,420,0,360,0C300,0,240,0,180,0C120,0,60,0,30,0L0,0Z'

  let wave: string = wave1

  onMount(() => {
    document.addEventListener('scroll', () => {
      wave = window.scrollY > 500 ? wave1 : wave2
    })
  })
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .hero {
    position: relative;
    height: 70vh;
    z-index: 2;

    .g-wrapper {
      max-width: 1200px;
    }

    h1 span {
      display: block;
      font-size: 200px;
      font-family: 'Oswald';
      line-height: 1;
      text-transform: uppercase;

      @include notDesktop {
        font-size: 60px;
      }
    }

    .reveal {
      color: #0000;
      --g: no-repeat linear-gradient(var(--colorBrand) 0 0) 0 0;
      background: var(--g), var(--g);
      background-size: 0 100%;
      -webkit-background-clip: padding-box, text;
      background-clip: padding-box, text;
      -webkit-box-decoration-break: clone;
      box-decoration-break: clone;
      animation:
        t 1.2s 0.5s both,
        b 1.2s 1.3s both;

      &.delay {
        animation-delay: 2s;
      }
    }

    @keyframes t {
      to {
        background-size: 150% 100%;
      }
    }
    @keyframes b {
      to {
        background-position:
          -200% 0,
          0 0;
      }
    }
  }

  .waves {
    position: relative;
    width: 100%;
    height: 100px;
    background-color: white;
    margin-top: -50px;
    z-index: 0;

    svg {
      filter: drop-shadow(0 10px 7px rgba(0, 0, 0, 0.3));

      path {
        transition: 1s ease-in-out;
      }
    }
  }
</style>

<div class="hero">
  <div class="g-wrapper">
    <h1>
      <span class="reveal">Potenciador</span>
      <span class="reveal delay">Digital</span>
    </h1>
  </div>
</div>

<div class="waves">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="var(--colorBackground)" fill-opacity="1" d={wave}></path></svg>
</div>
