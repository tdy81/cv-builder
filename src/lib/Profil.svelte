<script>
    import { marked } from 'marked'

    export let dataProfil;
    export let showEdit;
    export let showCollapse;

    function editItem() {
        showCollapse = !showCollapse;
    }
</script>

    <h2>Profil</h2>
    {#if showEdit}
        <button on:click={editItem}>
            collapse
        </button>
    {/if}

    {#if showCollapse}
    <div>

        {#if !showEdit}
        <div>{@html marked(dataProfil)}</div>
        {/if}

        {#if showEdit}
        <div>
            <label for="">Desc ( Enter + Enter saut de ligne)</label>
            <textarea bind:value={dataProfil}></textarea>
        </div>
        {/if}
    </div>
    {/if}