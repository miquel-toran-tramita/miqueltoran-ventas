<script lang="ts">
  import Svg from '@/components/Svg.svelte'

  export let activeTab: string
  export let tabList: any
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';
  .browser {
    position: relative;
    box-shadow: 0 0 60px 0 rgba(0, 0, 0, 0.3);
    border-radius: 12px 12px;
    overflow: hidden;
    padding: 0;
    transform: translateY(-50vh);
    z-index: 5;
    backdrop-filter: blur(10px);
    height: fit-content;
    .browser-topbar {
      width: 100%;
      height: 60px;
      background-color: var(--colorBrandSoft);
      display: flex;
      justify-content: space-between;
      align-items: center;

      .labels {
        display: flex;
        align-items: center;
        width: 100%;
        gap: 5px;
        padding-left: 10px;

        .label {
          display: flex;
          align-items: center;
          gap: 5px;
          padding: 0 15px;
          width: 100%;
          max-width: 200px;
          min-width: 50px;
          cursor: pointer;

          white-space: nowrap;
          overflow: hidden;
          text-overflow: ellipsis;

          border-radius: 8px;
          height: 40px;
          font-size: 14px;
          background-color: var(--colorBrandSoft);

          @include notDesktop {
            width: 30px;
            h5 {
              display: none;
            }
          }

          h5 {
            color: white;
            line-height: 1;
          }

          &:not(.active):hover {
            filter: brightness(1.2);
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
        padding: 0 10px;
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
        margin: 0 10px;
        border-radius: 8px;
        padding: 5px 16px;
      }
    }
  }
</style>

<div class="g-wrapper">
  <div class="browser">
    <div class="browser-topbar">
      <div class="labels">
        {#each tabList as tab}
          <button class="label" class:active={activeTab === tab.title} on:click={() => (activeTab = tab.title)}>
            <Svg name={tab.icon} fill="white" width="20" height="20" />
            <h5>{tab.title}</h5>
          </button>
        {/each}
      </div>

      <div class="browser-tools">
        <Svg name="minimize" />
        <Svg name="windows" />
        <Svg name="close" />
      </div>
    </div>
    <div class="tools">
      <div class="url-bar">{tabList.find((tab) => activeTab === tab.title).url}</div>
    </div>
    <div class="content">
      <slot />
    </div>
  </div>
</div>
