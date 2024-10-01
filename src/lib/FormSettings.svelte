<script>
    export let settingsType;
    export let settingsTheme;
    export let settingsFont;    
    export let currentTab;
	
	function onChangeType(event) {
		settingsType = parseFloat(event.currentTarget.value);
	}

    function onChangeTheme(event) {
        settingsTheme = event.currentTarget.value;
	}

    function onChangeFont(event) {
        settingsFont = event.currentTarget.value;
	}    

    function tabShow(el) {
        currentTab = el
    }
    
</script>
    <div class="text-xl text-black font-bold mb-4">Settings</div>

    <div class="border rounded-lg p-6 mb-6">
        <div class="font-bold mb-4">Types</div>
        <div class="flex mb-8">
            <div class="mr-8">
                <label>
                    <input on:change={onChangeType} type="radio" name="amount" value="0" checked /> 
                    Minimal
                </label>
            </div>
            <div class="mr-8">
                <label>
                    <input on:change={onChangeType} type="radio" name="amount" value="1" /> 
                    Standard
                </label>
            </div>
            <div class="mr-8">
                <label>
                    <input on:change={onChangeType} type="radio" name="amount" value="2" /> 
                    Graphique
                </label>
            </div>
        </div>
        <div class="font-bold mb-4">Thèmes</div>
        <div class="flex mb-8">
            <div class="mr-8">
                <label>
                    <input on:change={onChangeTheme} type="radio" name="theme" value="theme-1" checked /> 
                    Default
                </label>
            </div>
            <div class="mr-8">
                <label>
                    <input on:change={onChangeTheme} type="radio" name="theme" value="theme-2" /> 
                    Highlight
                </label>
            </div>
        </div>
        <div class="font-bold mb-4">Fonts</div>
        <div class="flex mb-8">
            <div class="mr-8">
                <label>
                    <input on:change={onChangeFont} type="radio" name="font" value="font-serif" checked /> 
                    Serif
                </label>
            </div>
            <div class="mr-8">
                <label>
                    <input on:change={onChangeFont} type="radio" name="font" value="font-sans-serif" /> 
                    Sans serif
                </label>
            </div>
        </div>
    </div>

    <div class="flex justify-end">
        <div>
            <button type="button" class="px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={() => tabShow(0)}>Suivant</button>
        </div>
    </div>
