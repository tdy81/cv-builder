<script>
    export let dataLangs;
    export let showEdit;
    export let showCollapse;

    let newName= '';
    let newPercent= '';

    function addItem() {
        dataLangs = [...dataLangs, {name: newName, percent: newPercent}];
        newName = '';
        newPercent = '';
    }

    function deleteItem(index) {
        dataLangs.splice(index, 1);
        dataLangs = dataLangs;
    }

    function editItem() {
        showCollapse = !showCollapse;
    }
</script>

<div>
    <h2>Langues</h2>
    {#if showEdit}
    <button on:click={editItem}>
        collapse
    </button>
    {/if}
    
    {#if showCollapse}
    <div>

    {#each dataLangs as item, index}
    <div>
        <div>{item.name}</div>
        {#if showEdit}
        <button class="btn-remove" on:click={ () => deleteItem(index) }>&#x2715</button>
        {/if}
    </div>
    {/each}

    {#if showEdit}
    <form on:submit|preventDefault={addItem}>
        <div>
            <label for="">Name</label>
            <input type="text" bind:value={newName}>
        </div>

        <button type="submit">Add item</button>
    </form>
    {/if}

    </div>
    {/if}
</div>