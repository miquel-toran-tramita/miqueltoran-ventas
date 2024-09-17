<script lang="ts">
</script>

<style lang="scss">
  .horizontal-slides {
    position: relative;
    height: 70vh;
    width: 100%;
    display: flex;
    overflow-x: scroll;
    scroll-snap-type: x mandatory;
    background-color: var(--colorBackground);
    z-index: 2;

    :global(.slide) {
      min-width: 100vw;
      scroll-snap-align: center;
    }
  }
</style>

<div class="horizontal-slides">
  <slot></slot>
</div>
