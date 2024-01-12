<script>
    import { marked } from 'marked'

    export let dataMaster;
    export let showEdit;
    export let showCollapse;

    let newName= '';
    let newDesc= '';
    let newDate= '';
    let newPlace = '';

    function addItem() {
        dataMaster = [...dataMaster, {name: newName, desc: newDesc, place: newPlace, date: newDate}];
        newName = '';
        newPlace = '';
        newDate = '';
        newDesc = '';
    }

    function deleteItem(index) {
        dataMaster.splice(index, 1);
        dataMaster = dataMaster;
    }

    function editItem() {
        showCollapse = !showCollapse;
    }
</script>

<div>
    <h2>Formations</h2>
    {#if showEdit}
    <button on:click={editItem}>
        collapse
    </button>
    {/if}

    {#if showCollapse}
    <div>

    {#each dataMaster as item, index}
    <div>
        <h3>{item.name}</h3>
        <div>{item.place}</div>
        <div>{item.date}</div>
        <div>{@html marked(item.desc)}</div>
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
        <div>
            <label for="">Place</label>
            <input type="text" bind:value={newPlace}>
        </div>
        <div>
            <label for="">Date</label>
            <input type="text" bind:value={newDate}>
        </div>
        <div>
            <label for="">Desc ( - lorem ipsum... ) press Enter</label>
            <textarea bind:value={newDesc}></textarea>
        </div>

        <button type="submit">Add item</button>
    </form>
    {/if}

    </div>
    {/if}
</div>