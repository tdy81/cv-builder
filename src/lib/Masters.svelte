<script>
  export let masters;
</script>

{#if masters.length}  
<div class="bloc-masters mb-8">
  <div class="text-lg font-bold mb-2">Etudes</div>
  <div class="w-4 h-0.5 bg-black mb-4 sep"></div>
  {#each masters as item, index}
    <div class="mb-3">
      <div class="font-bold">{item.title}</div>
      <div>{item.location} - {item.dateStart} à {item.dateEnd}</div>
    </div>
    {/each}
</div>
{/if}