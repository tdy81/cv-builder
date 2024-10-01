<script>
  export let skills;
</script>

{#if skills.length}
<div class="bloc-skills mb-8">
  <div class="text-lg font-bold mb-2">Compétences</div>
  <div class="w-4 h-0.5 bg-black mb-4 sep"></div>
  <ul>
    {#each skills as item, index}
    <li>- {item.name}</li>
    {/each}
  </ul>
</div>
{/if}