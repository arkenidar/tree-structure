<script>
export let tree
export let initial=false
$: opened=initial
function toggle(event){ opened=!opened }
</script>
<main on:click|stopPropagation={toggle} 
class="{ opened ? 'padding' : ''}" >
[{#each tree as subtree}
    {#if Array.isArray(subtree) }
        <svelte:self tree={subtree} initial={false}/>
    {:else}
        {subtree}
    {/if}
    {#if opened}<br>{/if}
{/each}]
</main>
<style>
main { border: solid 1px black; display: inline-block; margin: 5px; }
.padding { padding-left: 1cm; }
</style>