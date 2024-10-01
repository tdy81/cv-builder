<script>
  export let langs;
</script>

{#if langs.length}
<div class="mb-8">
<div class="text-lg font-bold mb-2">Langues</div>
  <div class="w-4 h-0.5 bg-black mb-4 theme-sep"></div>
  <ul>
    {#each langs as item, index}
    <li>- {item.name}</li>
    {/each}
</ul>
</div>
{/if}