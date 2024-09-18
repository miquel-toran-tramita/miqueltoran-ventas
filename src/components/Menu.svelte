<script lang="ts">
  import { onMount } from 'svelte'

  let HTMLMenu: HTMLElement
  let active: boolean = false

  onMount(() => {
    document.addEventListener('scroll', () => {
      const distance = HTMLMenu.getBoundingClientRect().top

      active = distance <= 0
    })
  })
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .menu {
    width: 100%;
    margin-top: calc(25vh - 100px);
    height: 100px;
    z-index: 10;
    //border-bottom: 1px solid var(--colorText);

    @include desktop {
      position: sticky;
      top: 0px;
      backdrop-filter: grayscale(1);
    }

    &.active {
      a {
        opacity: 1 !important;
      }
    }

    .g-wrapper {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100%;
      max-width: 1200px;

      .logo,
      a {
        color: var(--colorText3);
      }

      .logo {
        transition: 0.3s ease;
        font-size: 40px;
        font-family: 'Oswald';
        margin-left: 8px;

        @include notDesktop {
          font-size: 20px !important;
        }
      }

      ul {
        display: flex;
        align-items: center;
        gap: 20px;

        a {
          transition: 0.3s ease;
          font-family: 'Oswald';
          font-size: 30px;
          opacity: 0;
        }
      }
    }
  }
</style>

<div class="menu" class:active bind:this={HTMLMenu}>
  <div class="g-wrapper">
    <button on:click={() => window.scrollTo(0, 0)}>
      <h2 class="logo">Miquel Torán</h2>
    </button>
  </div>
</div>
