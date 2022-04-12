<script>
    var ms = 0
    var i = 0
    let display = "0.00"
    
    function Seconds() {
        if (i == 1) {
            ms += 1
            display = ms.toString().substring(0, ms.toString().length - 2) + "." + ms.toString().substring(ms.toString().length - 2, ms.toString().length);
            if (display[0] == "."){
                display = "0".concat(display)
            }
        }
    }
    function toggle(){
        if (i == 0){
            i = 1
        } else {
            i = 0
        }
    }
    function reset(){
        ms = 0
        display = "0.00"
    }
    setInterval(Seconds, 10)

</script>

<h1 class="text-blue-500">Welcome to SvelteKit</h1>
<p>Visit <a class="hover:underline" href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>You are here <b class="text-blue-500">{display}</b> s</p>
<div class="flex space-x-4">
    <button on:click={toggle} class="transition-colors duration-300 text-gray-500 {i == 0 ? 'bg-gray-100 hover:bg-gray-200' : 'bg-gray-300'} rounded px-3 py-2">{#if i == 0}Start{:else}Stop{/if}</button>
    <button on:click={reset} class="text-white transition-colors duration-300 bg-orange-400 rounded px-3 py-2 hover:bg-orange-300">Reset</button>
</div>
