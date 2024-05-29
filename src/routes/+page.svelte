<script>
    import Comp1 from "$lib/Comp1.svelte";
    const props = {
        x: 'Sakktábla'
    }
</script>

<h1>Gyökér elem</h1>
<div class="c1c"><Comp1 {...props}/></div>
<style>
    div.c1c {
        text-align: center;
    }
    h1 {
        text-align: center;
    }
</style>