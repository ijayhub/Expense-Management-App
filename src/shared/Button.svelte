<script>
    export let isDisabled=false;
    export let type='submit'
</script>
<button class={type} class:disabled={isDisabled}>
    <slot></slot>
</button>

<style>
    button{
        padding:6px;
        border-radius: 5px;
        width:100%;
        border:1px solid #009579;
        background-color:white;
        color:#009579;
        letter-spacing:2px;
        text-transform: uppercase;
        margin-top:5px;
    }
    button:hover{
        background-color:#009579;
        color:white
    } 
    .disabled{
        color:lightgray;
        border:1px solid lightgray;
    }


</style>