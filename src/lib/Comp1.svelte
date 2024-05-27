<script>
    export let n
    const t = Array(Number(n**2)).fill().map((v, i) => i)
</script>

<h4>Comp1</h4>
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
    div.c {
        margin: 20px;
        display: inline-grid;
    }
    div.c div {
        text-align: center;
        display: inline-block;
        padding: 20px;
    }
    div.c div.x0 {
        background-color: black;
        color: aliceblue;
    }
    div.c div.x1 {
        background-color: rgb(255, 255, 255);
        color: rgb(5, 5, 5);
    }
</style>