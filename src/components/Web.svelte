<script lang="ts">
  import Svg from '@/components/Svg.svelte'
</script>

<style lang="scss">
  .browser {
    position: relative;
    box-shadow: 0 0 60px 0 rgba(0, 0, 0, 0.3);
    border-radius: 12px 12px;
    overflow: hidden;
    padding: 0;
    transform: translateY(-50vh);
    z-index: 5;
    .browser-topbar {
      width: 100%;
      height: 50px;
      background-color: var(--colorBrandSoft);
      display: flex;
      justify-content: space-between;
      align-items: center;

      .labels {
        display: flex;
        align-items: center;
        width: 100%;
        gap: 5px;

        .label {
          display: flex;
          align-items: center;
          padding: 0 20px;
          width: 100%;
          max-width: 200px;
          min-width: 100px;
          cursor: pointer;

          white-space: nowrap;
          overflow: hidden;
          text-overflow: ellipsis;

          border-radius: 8px;
          height: 40px;
          font-size: 14px;
          color: white;

          &.hover {
            border: 2px solid red;
          }

          &.active {
            background-color: var(--colorBrand);
          }
        }
      }

      .browser-tools {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
        padding: 0 15px;
        :global(svg) {
          fill: white;
          width: 20px;
          height: 20px;
        }
      }
    }
    .tools {
      background-color: var(--colorBrand);
      height: 50px;
      display: flex;
      align-items: center;

      .url-bar {
        background-color: white;
        width: 100%;
        margin: 0 15px;
        border-radius: 8px;
        padding: 5px 20px;
      }
    }
    .content {
      margin-top: -1px;
    }
  }
</style>

<div class="g-wrapper">
  <div class="browser">
    <div class="browser-topbar">
      <div class="labels">
        <div class="label">Reflexión</div>
        <div class="label active">Mi historia</div>
      </div>

      <div class="browser-tools">
        <Svg name="minimize" />
        <Svg name="windows" />
        <Svg name="close" />
      </div>
    </div>
    <div class="tools">
      <div class="url-bar">www.miqueltoran.com</div>
    </div>
    <div class="content">
      <slot />
    </div>
  </div>
</div>
