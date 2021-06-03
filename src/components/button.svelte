<script>

    import {Button} from 'sveltestrap';
    

    export let kind = "default";
    export let value = "";
    export let disabled = false;
    export let loading = false;
    let spin = false;
    

    function handleClick(){
        spin = true;
        return (setTimeout(() => {
            spin = false;
        },2000))
    }

    $: buttonProps ={
        value,
        disabled,
        loading,
        class: [
            kind && `button--${kind}`
        ]
    }
</script>

{#if kind == "default"}
    <Button color="primary">{value}</Button>
{:else if loading}
    <Button {...buttonProps} color="primary" on:click={handleClick} >
        {spin ? "wait" : `${value}`}
    </Button>
{:else}
    <Button {...buttonProps} color="primary">{value}</Button>
{/if}




<style>
    :global(.button--nav){
        background-color: red !important;
        border-color: red !important;
        width: 175px;
    }
    :global(.button--header){
        background-color: greenyellow !important;
        border-color: greenyellow !important;
        width: 125px;
    }
</style>