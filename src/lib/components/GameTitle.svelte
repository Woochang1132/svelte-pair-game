<script>
    import GameScore from "./GameScore.svelte";
    import GamePlay from "./GamePlay.svelte";
    
    let {title} = $props()
    let page = $state('title');
</script>


<main>
    {#if page === 'title'}
    <section class="itim-regular">
    <h1>{title}</h1>
    <div class="btn-group">
        <button class="btn" on:click={() => page = 'play'}>Start</button>
        <button class="btn" on:click={() => page = 'score'}>Score</button>
    </div>
    </section>
    {:else if page === 'play'}
     <GamePlay />
    {:else if page === 'score'}
     <GameScore bind:page={page}/>
    {/if}
     
</main>

<style lang="scss">
    section{
        h1{
            font-size: 16vw;
            color: #ff3e00;
            -webkit-text-stroke: 10px rgba(0,0,0, 0.5);
            paint-order: stroke fill;
        }
      .btn-group {
      display: flex;
      flex-direction: column;
      margin-top: 40px;
      button {
        padding: 10px;
        font-size: 32px;
        background: transparent;
        border: none;
        &:hover {
          text-decoration: underline;
        }
      }
    }
  }
</style>