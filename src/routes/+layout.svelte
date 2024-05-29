<script>
    import { navigating } from '$app/stores'
    $: currentRoute = $navigating?.to.route.id || currentRoute
    $: prevRoute = $navigating?.from.route.id || prevRoute
    const menu = [{name: 'Gyökér', href: '/'}, {name: '1. oldal', href: '/page1'}, {name: '2. oldal', href: '/page2'}]
</script>
<div class=header>
    {#each menu as item}
        <a class={currentRoute === item.href ? 'active' : prevRoute === item.href ? 'prev' : ''} href={item.href}>{item.name}</a>
    {/each}
</div>
<div class=content>
    <slot/>
</div>
<div class=footer>Footer</div>
<style>
    div.header {
        width: 100%;
        position: fixed;
        top: 0px;
        background-color: black;
        color: aliceblue;
        padding: 4px;
    }
    a {
        color: white;
        padding-left: 20px;
        display: inline-block;
        all: unset;
        padding: 4px;
        padding-left: 20px;
        padding-right: 20px;
        background-color: rgb(60, 56, 56);
        cursor: pointer;
    }
    a.active {
        background-color: rgb(255, 255, 255);
        color: rgb(45, 66, 85);
    }
    a.prev {
        color: rgb(211, 194, 194);
        background-color: rgb(60, 56, 56);
    }
    div.content {
        border-radius: 12px;
        border:solid 10px rgb(66, 62, 62);
        padding: 20px;
        margin: 30px;
        margin-top : 46px;
        box-shadow: 4px 4px 16px black;
        background-color: rgb(238, 230, 221);
    }
    div.footer {
        width: 100%;
        padding: 0px;
        background-color: black;
        color: aliceblue;
        position: fixed;
        bottom: 0;
        text-align: center;
    }
</style>