<script lang="ts">
  import Web from '@/components/Web.svelte'
  import TextoVenta from '@/components/TextoVenta.svelte'

  let activeTab = 'TextoVenta'
</script>

<Web bind:activeTab>
  {#if activeTab === 'TextoVenta'}
    <TextoVenta />
  {/if}
</Web>
