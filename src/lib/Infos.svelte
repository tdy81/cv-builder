<script>
    export let dataInfos;
    export let showEdit;
    export let showCollapse;

    function editItem() {
        showCollapse = !showCollapse;
    }
</script>
    {#if showEdit}
    <h2>Infos</h2>
    {/if}

    {#if showEdit}
        <button on:click={editItem}>
            collapse
        </button>
    {/if}

    {#if showCollapse}
    <div>

        {#if !showEdit}
        <img src={dataInfos.media} alt="" width="80">
        <h1 class="mb">{dataInfos.name} <small>{dataInfos.job}</small></h1>
        <div class="mb">{dataInfos.age}</div>
        <div class="mb">
            <strong>
            {dataInfos.phone}
            <br>
            {dataInfos.email}
            </strong>
        </div>
        <div class="mb">{dataInfos.address}</div>
        {/if}

        {#if showEdit}
        <div>
            <label for="">Image ( ex : https://placehold.co/80x80)</label>
            <input type="text" bind:value={dataInfos.media}>
        </div>
        <div>
            <label for="">Name</label>
            <input type="text" bind:value={dataInfos.name}>
        </div>
        <div>
            <label for="">Job</label>
            <input type="text" bind:value={dataInfos.job}>
        </div>
        <div>
            <label for="">Age</label>
            <input type="text" bind:value={dataInfos.age}>
        </div>
        <div>
            <label for="">Address</label>
            <input type="text" bind:value={dataInfos.address}>
        </div>
        <div>
            <label for="">Email</label>
            <input type="text" bind:value={dataInfos.email}>
        </div>
        <div>
            <label for="">Phone</label>
            <input type="text" bind:value={dataInfos.phone}>
        </div>
        {/if}

    </div>
    {/if}