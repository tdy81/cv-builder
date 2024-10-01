<script>

    export let currentTab;
    
    export let master = {
        title: "",
        location: "",
        dateStart: "",
        dateEnd: "",
        show: true,
    }

    export let masters

    function addItem() {
        masters = [...masters, {...master}];
        //console.log(masters)
    }

    function deleteItem(index) {
        masters.splice(index, 1);
        masters = masters;
    }
    
    function collapseItem(index) {
        let el = masters[index]
        el.show = !el.show
        masters = masters;
    }    
    
    function tabShow(el) {
        currentTab = el
    }
</script>

<div class="text-xl text-black font-bold mb-4">Etudes</div>

{#each masters as item, index}
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
            <label for="" class="block text-sm text-black font-medium mb-1">Name</label>
            <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.title}>
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
    </div>
    {/if}
</div>
{/each}

<div class="flex justify-between">
    <div><button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => addItem()}>Add item</button></div>
    <div>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-white text-black border border-black hover:bg-black hover:border-black hover:text-white rounded" on:click={() => tabShow(1)}>Précédent</button>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => tabShow(3)}>Suivant</button>
    </div>
</div>
