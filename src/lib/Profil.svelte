<script>
    export let infos;
</script>

{#each infos as item, index} 
{#if item.desc}
<div class="mb-8">
    <div class="text-lg font-bold mb-2">Profil</div>
    <div class="w-4 h-0.5 bg-black mb-4 theme-sep"></div>
    <div>
        <div>{@html item.desc}</div>
    </div>
</div>
{/if} 
{/each}
