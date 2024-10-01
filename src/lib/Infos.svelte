<script>
    export let infos;

    import avatar from '../assets/avatar.jpg';
</script>

{#each infos as item, index}
<div class="bloc-infos mb-8">
  <div class="w-24 h-24 rounded-full overflow-hidden mb-4 avatar bg-slate-100">
    {#if item.avatar}
      <img class="object-cover h-full w-full" src="{item.avatar}" alt="" />
    {:else}
      <img class="object-cover h-full w-full" src="{avatar}" alt="" />
    {/if}
  </div>
  <div class="font-bold text-2xl">{item.name}</div>
  <div class="text-lg">{item.job}</div>
</div>
{/each}