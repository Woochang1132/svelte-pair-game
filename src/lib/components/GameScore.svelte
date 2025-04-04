<script>
    let {page = $bindable()} = $props()
</script>

<main>
    <h1>GameScore</h1>
    <button on:click={() => page = 'title'}>Back to home</button>
</main>