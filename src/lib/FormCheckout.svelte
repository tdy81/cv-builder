<script>
    import html2pdf from 'html2pdf.js'   
    export let currentTab;

    function tabShow(el) {
    currentTab = el
    }

    async function handlePrint() {
    const element = document.getElementById('wrap-preview');

    var opt = {
        margin: 0,
        filename: 'cv.pdf',
        image: { type: 'jpeg', quality: 1 },
        html2canvas: { scale: 4 }
    };
    html2pdf().set(opt).from(element).save();
    }
</script>

<div class="text-xl text-black font-bold mb-4">Checkout</div>

<div class="border rounded-lg p-6 mb-6">
    <div class="flex justify-between mb-4">
        <div>CV.pdf</div>
        <div class="font-bold">1€</div>
    </div>
    <button type="button" class="w-full mb-4 px-6 py-3 uppercase text-xs bg-white text-black border border-black hover:bg-black hover:border-black hover:text-white rounded">Button stripe</button>
    <button type="button" class="w-full px-6 py-3 uppercase text-xs bg-black text-white border border-black hover:bg-white hover:border-black hover:text-black rounded" on:click={handlePrint}>Download PDF</button>
</div>
