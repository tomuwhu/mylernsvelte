<script>
    import Comp1 from "$lib/Comp1.svelte";
    var props
</script>

<h1>1. oldal</h1>
{#each Array(4).fill() as _, i}
    { props = {n: Number(i + 2), x: Number(i + 2)}, '' }
    <div class="c1c">
        <Comp1 {...props} />
    </div>
{/each}
<style>
    div.c1c {
        text-align: center;
    }
</style>