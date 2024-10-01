<script>

    export let currentTab = 0;
    
    export let interest = {
        name: "",
        show: true,
    }

    export let interests

    function addItem() {
        interests = [...interests, {...interest}];
    }

    function deleteItem(index) {
        interests.splice(index, 1);
        interests = interests;
    }
    
    function collapseItem(index) {
        let el = interests[index]
        el.show = !el.show
        interests = interests;
    }    
    
    function tabShow(el) {
        currentTab = el
    }
</script>

<div class="text-xl text-black font-bold mb-4">Centres d'intérêt</div>

{#each interests as item, index}
<div class="border rounded-lg p-6 mb-6">
    <div>
        <label for="" class="block text-sm text-black font-medium mb-1">Name</label>
        <div class="flex gap-4">
            <div class="grow"><input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.name}></div>
            <div><button type="button" class="h-full border hover:border-black rounded py-1 px-2" on:click={ () => deleteItem(index) }>&#x2715</button></div>
        </div>
    </div>
</div>
{/each}

<div class="flex justify-between">
    <div><button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => addItem()}>Add item</button></div>
    <div>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-white text-black border border-black hover:bg-black hover:border-black hover:text-white rounded" on:click={() => tabShow(6)}>Précédent</button>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => tabShow(5)}>Suivant</button>
    </div>
</div>
