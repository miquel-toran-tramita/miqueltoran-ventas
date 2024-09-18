<script lang="ts">
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .bg {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100vh;
    background-image: url('/assets/bg3.png');
    filter: invert(1);
    opacity: 0.1;
    background-size: cover;
    background-position: center;
  }

  .hero {
    position: relative;
    min-height: 75vh;
    z-index: 2;

    .g-wrapper {
      max-width: 1200px;
    }

    h1 span {
      display: block;
      font-size: 200px;
      font-family: 'Oswald';
      line-height: 1;

      @include notDesktop {
        font-size: 60px;
      }
    }

    .web {
      font-size: 300px;
      filter: brightness(0.7);

      @include notDesktop {
        font-size: 200px;
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
</style>

<div class="bg"></div>
<div class="hero">
  <div class="g-wrapper">
    <h1>
      <span class="reveal potenciador">POTENCIADOR</span>
      <span class="reveal delay web">WEB</span>
    </h1>
  </div>
</div>
