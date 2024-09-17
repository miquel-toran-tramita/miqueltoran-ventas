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
    position: sticky;
    top: 0px;
    width: 100%;
    backdrop-filter: blur(2px);
    margin-top: calc(30vh - 60px);
    height: 80px;
    z-index: 10;
    background-color: var(--colorBackground);

    .g-wrapper {
      max-width: 1200px;
    }

    &.active {
      transition: 0.3s ease;
      background-color: rgba(0, 0, 0, 0.5);

      .logo,
      a {
        opacity: 1 !important;
      }
    }

    .g-wrapper {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100%;

      .logo {
        transition: 0.3s ease;
        font-size: 40px;
        font-family: 'Oswald';
        margin-left: 8px;
        color: var(--colorText3);

        @include notDesktop {
          font-size: 20px !important;
        }
      }

      ul {
        display: flex;
        align-items: center;
        gap: 20px;

        a {
          color: var(--colorText3);
          transition: 0.3s ease;
          font-family: 'Oswald';
          font-size: 20px;
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

    <ul>
      <li>
        <a href="">Inicio</a>
      </li>
      <li>
        <a href="">Que hago</a>
      </li>
    </ul>
  </div>
</div>
