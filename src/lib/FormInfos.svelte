<script>
    export let infos;
    export let currentTab;
    let fileinput;

    function tabShow(el) {
        currentTab = el
    }

    const onFileSelected =(e)=>{
        let image = e.target.files[0];
        let reader = new FileReader();
        reader.readAsDataURL(image);
        reader.onload = e => {
            infos[0].avatar = e.target.result
        };
    }    
</script>
<div>
    <div class="text-xl text-black font-bold mb-4">Profil</div>
    <div class="border rounded-lg p-6 mb-6">
        <div class="mb-4">
            <label for="" class="block text-sm text-black font-medium mb-1">Photo</label>
            <input style="display:none" type="file" accept=".jpg, .jpeg, .png" on:change={(e)=>onFileSelected(e)} bind:this={fileinput}>
            <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={()=>{fileinput.click();}}>Choose Image</button>
        </div>
        {#each infos as item, index}
        <div class="mb-4">
            <label for="" class="block text-sm text-black font-medium mb-1">Nom & Prénom</label>
            <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.name}>
        </div>
        <div class="mb-4">
            <label for="" class="block text-sm text-black font-medium mb-1">Métier</label>
            <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.job}>
        </div>
        <div class="mb-4">
            <label for="" class="block text-sm text-black font-medium mb-1">Adresse</label>
            <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.address}>
        </div>
        <div class="flex gap-4">
            <div class="basis-1/2 mb-4">
                <label for="" class="block text-sm text-black font-medium mb-1">Cp</label>
                <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.cp}>
            </div>
            <div class="basis-1/2 mb-4">
                <label for="" class="block text-sm text-black font-medium mb-1">City</label>
                <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.city}>
            </div>
        </div>
        <div class="flex gap-4">
            <div class="basis-1/2 mb-4">
                <label for="" class="block text-sm text-black font-medium mb-1">Email</label>
                <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.email}>
            </div>
            <div class="basis-1/2 mb-4">
                <label for="" class="block text-sm text-black font-medium mb-1">Phone</label>
                <input type="text" class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500" bind:value={item.phone}>
            </div>
        </div>
        <div>
            <label for="" class="block text-sm text-black font-medium mb-1">Desc</label>
            <textarea class="block border focus:border-slate-900 outline-none rounded w-full p-3 text-sm text-slate-500 min-h-24" bind:value={item.desc}></textarea>
        </div>
        {/each}
    </div>
    <div class="flex justify-end">
        <div class="w-auto">
            <button type="button" class="px-6 py-3 uppercase text-xs bg-white text-black border border-black hover:bg-black hover:border-black hover:text-white rounded" on:click={() => tabShow(5)}>Précédent</button>
            <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => tabShow(1)}>Suivant</button>
        </div>
    </div>
</div>
