<script>
    var seconds = 0
    let display = "0.000"
    function Seconds() {
        seconds += 0.001;
        display = seconds.toFixed(3)
    }
    var cancel = setInterval(Seconds, 1);
</script>

<h1 class="text-blue-500">Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>You are here <b class="text-blue-500">{display}</b> s</p>