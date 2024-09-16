<script lang="ts">
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .hero {
    height: 80vh;

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
</style>

<div class="hero">
  <div class="g-wrapper">
    <h1>
      <span class="reveal">Potenciador</span>
      <span class="reveal delay">Digital</span>
    </h1>
  </div>
</div>
