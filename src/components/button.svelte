<script>

    export let color1 = false;
    export let text;

</script>

{#if color1 == true }
    <button class="pink" on:click={() => text = "Clicked"}>{text}</button>    
{/if}


<style>
    .pink{
        background-color: pink;
    }
</style>