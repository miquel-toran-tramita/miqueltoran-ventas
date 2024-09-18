<style lang="scss">
  .web-container {
    background-color: white;
    width: 100%;

    .web {
      border: 2px solid red;
      border-radius: 8px;
      padding: 0;

      .window-container {
        margin: 10px;
        overflow: hidden;
        width: 200px;

        .window {
          position: relative;
          background-color: var(--colorBrand);
          border-radius: 8px;
          height: 50px;
          width: calc(100% - 30px);

          &.secondary {
            transform: translateX(15px);
            &:after {
              content: '';
              position: absolute;
              width: 50px;
              height: 150%;
              border-radius: 8px;
              background-color: var(--colorBrand);
              filter: brightness(0.7);

              top: 4px;
              transform: rotate(30deg);
            }
          }

          &:before {
            content: '';
            position: absolute;
            width: 50px;
            height: 150%;
            border-radius: 8px;
            background-color: var(--colorBrand);
            right: -20px;
            top: 4px;
            transform: rotate(-30deg);
          }
        }
      }
    }
  }
</style>

<div class="web-container">
  <div class="web g-wrapper">
    <div class="window-container">
      <div class="window" />
    </div>
    <div class="window-container">
      <div class="window secondary" />
    </div>
    <slot></slot>
  </div>
</div>
