<script>

    import {Button} from 'sveltestrap';
    export let navButton = false;
    export let headerButton = false;

</script>

{#if navButton == true }
    <Button class="navButton" >nav</Button>    
{:else if headerButton == true}
    <Button class="headerButton" >header</Button>
{:else}
    <Button color="primary">normal</Button>
{/if}



<style>
    :global(.navButton){
        background-color: red !important;
        border-color: red !important;
        width: 175px;
    }
    :global(.headerButton){
        background-color: greenyellow !important;
        border-color: greenyellow !important;
        width: 125px;
    }
</style>