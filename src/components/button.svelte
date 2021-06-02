<script>

    import {Button} from 'sveltestrap';
    

    export let kind = "default";
    export let value = "";

    $: buttonProps ={
        value,
        class: [
            kind && `button--${kind}`
        ]
    }
</script>

<Button {...buttonProps} color="primary">{value}</Button>



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