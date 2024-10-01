<script>
    //import { marked } from 'marked'
    export let xps;
</script>

{#if xps.length}
  <div class="bloc-xp">
      <div class="text-lg font-bold mb-2">Expériences</div>
      <div class="w-4 h-0.5 bg-black mb-4 sep"></div>
    {#each xps as item, index}
      <div class="mb-8">
        <div class="font-bold">{item.job}</div>
        <div>{item.location} - {item.dateStart} à {item.dateEnd}</div>
        <div class="whitespace-pre-wrap mt-2">{@html item.desc}</div>
      </div>
    {/each}
  </div>
{/if}