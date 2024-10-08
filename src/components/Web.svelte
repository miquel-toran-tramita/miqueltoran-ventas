<script lang="ts">
  import Svg from '@/components/Svg.svelte'

  export let activeTab: string
  export let tabList: any

  let minimize: boolean = false
  let close: boolean = false
  let windows: boolean = false
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';
  .browser {
    position: relative;
    transition: 0.3s ease;
    box-shadow: 0 0 60px 0 rgba(0, 0, 0, 0.7);
    border-radius: 12px 12px;
    margin-top: 50px;
    overflow: hidden;
    padding: 0;
    z-index: 5;
    backdrop-filter: blur(10px);
    height: fit-content;

    &.windows {
      transform: scale(0.7);
    }

    &.close {
      opacity: 0.2;
    }

    &.minimize {
      .content {
        height: 0;
      }
    }

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
          transition: 0.5s ease;
          display: flex;
          align-items: center;
          gap: 10px;
          padding: 0 10px;
          width: 100%;
          max-width: 200px;
          min-width: 40px;
          cursor: pointer;

          border-radius: 8px;
          height: 40px;
          font-size: 14px;
          background-color: var(--colorBrandSoft);

          @include notDesktop {
            &:not(.active) {
              width: 30px;
              h5 {
                display: none;
              }
            }
          }

          :global(svg) {
            flex-shrink: 0;
          }

          h5 {
            color: white;
            line-height: 1;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
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
        padding-right: 10px;
        gap: 10px;
        :global(svg) {
          fill: white;
          width: 20px;
          height: 20px;
        }

        button {
          display: flex;
          align-items: center;
          height: 100%;
        }

        @include notDesktop {
          gap: 2px;
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
        padding: 5px 12px;
      }
    }
  }
</style>

<div class="g-wrapper">
  <div class="browser" class:minimize class:close class:windows>
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
        <button on:click={() => (minimize = !minimize)}>
          <Svg name="minimize" />
        </button>

        <button on:click={() => (windows = !windows)}>
          <Svg name="windows" />
        </button>

        <button on:click={() => (close = !close)}>
          <Svg name="close" />
        </button>
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
