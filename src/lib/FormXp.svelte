<script>

export let currentTab;

export let xp = {
    job: "",
    location: "",
    dateStart: "",
    dateEnd: "",
    desc: "",
    show: true,
}

export let xps

function addItem() {
    xps = [...xps, {...xp}];
    console.log(xps)
}

function deleteItem(index) {
    xps.splice(index, 1);
    xps = xps;
}

function collapseItem(index) {
    let el = xps[index]
    el.show = !el.show
    xps = xps;
}    

function tabShow(el) {
    currentTab = el
}
</script>

<div class="text-xl text-black font-bold mb-4">Expérience</div>

{#each xps as item, index}
<div class="border rounded-lg p-6 mb-6">
    <div class="flex justify-between items-center mb-4 pb-4 border-b">
        <div>Item {index}</div>
        <div>
            <button type="button" class="border hover:border-black rounded py-1 px-2" on:click={ () => deleteItem(index) }>&#x2715</button>
            <button type="button" class="border hover:border-black rounded py-1 px-2" on:click={ () => collapseItem(index) }>&darr;</button>
        </div>
    </div>
    {#if item.show}
    <div>
        <div class="mb-4">
            <label for="" class="block text-sm text-black font-medium mb-1">Job</label>
            <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.job}>
        </div>
        <div class="mb-4">
            <label for="" class="block text-sm text-black font-medium mb-1">Location</label>
            <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.location}>
        </div>
        <div class="flex gap-4">
            <div class="basis-1/2 mb-4">
                <label for="" class="block text-sm text-black font-medium mb-1">Date start</label>
                <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.dateStart}>
            </div>  
            <div class="basis-1/2 mb-4">
                <label for="" class="block text-sm text-black font-medium mb-1">Date end</label>
                <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.dateEnd}>
            </div>
        </div>
        <div>
            <label for="" class="block text-sm text-black font-medium mb-1">Desc ( - lorem ipsum... ) press Enter</label>
            <textarea class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500 min-h-24" bind:value={item.desc}></textarea>
        </div>
    </div>
    {/if}
</div>
{/each}

<div class="flex justify-between">
    <div><button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => addItem()}>Add item</button></div>
    <div>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-white text-black border border-black hover:bg-black hover:border-black hover:text-white rounded" on:click={() => tabShow(0)}>Précédent</button>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => tabShow(2)}>Suivant</button>
    </div>
</div>
