<script>
    import GameScore from "./GameScore.svelte";
    import GamePlay from "./GamePlay.svelte";
    
    let {title} = $props()
    let page = $state('title');
</script>


<main>
    {#if page === 'title'}
    <section>
    <h1>{title}</h1>
    <div class="btn-group">
        <button on:click={() => page = 'play'}>Start</button>
        <button on:click={() => page = 'score'}>Score</button>
    </div>
    </section>
    {:else if page === 'play'}
     <GamePlay />
    {:else if page === 'score'}
     <GameScore bind:page={page}/>
    {/if}
     
</main>