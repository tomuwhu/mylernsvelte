<script>
    export let n = 8, x = 'névtelen rács komponens'
    const t = Array(Number(n**2)).fill().map((v, i) => i)
</script>

<h2>Komponens: {x}, n = {n}</h2>
<div class="c" style="grid-template-columns: repeat({n}, 1fr);">
{#each t as i}
    {#if n % 2 == 0}
        <div class="x{(i + Math.trunc(i / n)) % 2}">{i + 1}</div>
    {:else}
        <div class="x{i % 2}">{i + 1}</div>
    {/if}
{/each}
</div>

<style lang="scss">
    h2 {
        text-shadow: 1px 1px 3px gray;
        color: rgb(37, 66, 56);
    }
    div.c {
        margin: 20px;
        display: inline-grid;
    }
    div.c div {
        text-align: center;
        display: inline-block;
        padding: 20px;
        margin: 3px;
        border-radius: 7px;
        
    }
    div.c div.x0 {
        background-color: rgb(96, 91, 91);
        color: aliceblue;
        box-shadow: 1px 1px 6px rgb(0, 0, 0);
    }
    div.c div.x1 {
        background-color: rgb(255, 255, 255);
        color: rgb(5, 5, 5);
        box-shadow: 1px 1px 4px inset black;
    }
</style>