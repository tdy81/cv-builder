<script>
    export let infos;
</script>

{#each infos as item, index}
<div class="mb-8">
  <div class="text-lg font-bold mb-2">Contact</div>
  <div class="w-4 h-0.5 bg-black mb-4 theme-sep"></div>
  <div>
    <div>T : {item.phone}</div>
    <div>E : {item.email}</div>
    <div class="mt-2">{item.address}<br> {item.cp}, {item.city}</div>
  </div>
</div>
{/each}