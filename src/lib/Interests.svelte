<script>
  export let interests;
</script>

{#if interests.length}
<div class="mb-8">
  <div class="text-lg font-bold mb-2">Centres d'intérêt</div>
  <div class="w-4 h-0.5 bg-black mb-4 theme-sep"></div>
  <ul>
    {#each interests as item, index}
    <li>- {item.name}</li>
    {/each}
  </ul>
</div>
{/if}