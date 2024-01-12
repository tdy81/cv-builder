<script>
    export let dataSkills;
    export let showEdit;
    export let showCollapse;

    let newName= '';
    let newPercent= '';

    function addItem() {
        dataSkills = [...dataSkills, {name: newName, percent: newPercent}];
        newName = '';
        newPercent = '';
    }

    function deleteItem(index) {
        dataSkills.splice(index, 1);
        dataSkills = dataSkills;
    }

    function editItem() {
        showCollapse = !showCollapse;
    }
</script>

<div>
    <h2>Compétences</h2>
    {#if showEdit}
    <button on:click={editItem}>
        collapse
    </button>
    {/if}
    
    {#if showCollapse}
    <div>

    <ul>
    {#each dataSkills as item, index}
        <li>
            <div>{item.name}</div>
            {#if showEdit}
            <button class="btn-remove" on:click={ () => deleteItem(index) }>&#x2715</button>
            {/if}
        </li>
    {/each}
    </ul>

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