<script lang="ts">
  import Web from '@/components/Web.svelte'
  import TextoVenta from '@/components/TextoVenta.svelte'

  const tabList = [
    {
      title: 'Cómo hacer una web',
      icon: 'web',
      url: 'www.miqueltoran.com',
    },
    {
      title: 'Ejemplo Inmobiliaria',
      icon: 'logo',
      url: 'www.tramita.info',
    },
  ]

  let activeTab = tabList[0].title
</script>

<style lang="scss">
  iframe {
    width: 100%;
    height: 70vh;
  }
</style>

<Web {tabList} bind:activeTab>
  {#if activeTab === tabList[0].title}
    <TextoVenta />
  {/if}
  {#if activeTab === tabList[1].title}
    <iframe src="https://nousamoscorbata.vercel.app/" frameborder="0" allowfullscreen></iframe>
  {/if}
</Web>
