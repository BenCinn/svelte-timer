<script>
    var ms = 0
    var i = 0
    let display = "0.000"
    
    function Seconds() {
        if (i == 1) {
            ms += 1
            let act = ms.toString()
            act = act.padStart(4, "0")
            display = act.substring(0, act.length - 3) + "." + act.substring(act.length - 3, act.length);
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
        display = "0.000"
    }
    setInterval(Seconds, 1)

</script>

<h1 class="text-blue-500">Welcome to SvelteKit</h1>
<p>Visit <a class="hover:underline" href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>You are here <b class="text-blue-500">{display}</b> s</p>
<div class="flex space-x-4">
    <button on:click={toggle} class="transition-colors duration-300 text-gray-500 {i == 0 ? 'bg-gray-100 hover:bg-gray-200' : 'bg-gray-300'} rounded px-3 py-2">{#if i == 0}Start{:else}Stop{/if}</button>
    <button on:click={reset} class="text-white transition-colors duration-300 bg-orange-400 rounded px-3 py-2 hover:bg-orange-300">Reset</button>
</div>
