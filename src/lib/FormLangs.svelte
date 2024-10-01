<script>

    export let currentTab = 0;
    
    export let lang = {
        name: "",
        show: true,
    }

    export let langs

    function addItem() {
        langs = [...langs, {...lang}];
    }

    function deleteItem(index) {
        langs.splice(index, 1);
        langs = langs;
    }
    
    function collapseItem(index) {
        let el = langs[index]
        el.show = !el.show
        langs = langs;
    }    
    
    function tabShow(el) {
        currentTab = el
    }
</script>

<div class="text-xl text-black font-bold mb-4">Langues</div>

{#each langs as item, index}
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
        <button type="button" class="px-6 py-3 uppercase text-xs bg-white text-black border border-black hover:bg-black hover:border-black hover:text-white rounded" on:click={() => tabShow(3)}>Précédent</button>
        <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => tabShow(7)}>Suivant</button>
    </div>
</div>
