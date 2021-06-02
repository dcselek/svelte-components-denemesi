<script>

    import {Button} from 'sveltestrap';
    

    export let kind = "";
    export let value = "";
    export let disabled = false;
    export let loading = false;

    $: buttonProps ={
        value,
        disabled,
        loading,
        class: [
            kind && `button--${kind}`
        ]
    }
</script>

{#if kind != ""}
    <Button {...buttonProps} color="primary">{value}</Button>
{:else}
    <Button color="primary">{value}</Button>
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