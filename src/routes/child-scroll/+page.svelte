<script lang="ts">
	import { onMount } from 'svelte';
    import { scroll } from '../../stores/scroll'

    let main: HTMLElement

    const saveScroll = () => $scroll = main.scrollTop

    const content = `This
    is
    just
    a
    simple
    test
    to
    see
    if
    scroll
    position
    is
    remembered
    from
    each
    time
    this
    page
    is
    entered`

    onMount(() => {
        main.scroll({ top: $scroll })
    })
</script>

<h1>Child Scroll Page</h1>

<h2>Scroll element</h2>
<main bind:this={main} on:scroll={saveScroll}>
    {#each content.split('\n') as line}
        <div class="flex-child">
            {line}
        </div>
    {/each}
</main>

<style>
    main {
        width: 400px;
        height: 400px;
        padding: 5px 10px;
        display: flex;
        flex-direction: column;
        gap: 5px;
        overflow-y: auto;
        background: #0005;
    }
    .flex-child {
        padding: 20px;
        border-radius: 40px;
        background: lightblue;
    }
</style>