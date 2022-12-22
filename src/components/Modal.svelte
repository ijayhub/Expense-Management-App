<script>
    import Title from "../shared/Title.svelte";
    export let showModal = false
</script>
{#if showModal}
<div class="backdrop" >
    <div class="modal">
        <div class="head-modal" >
            <Title title="Add Expenses"/>
            <button class="close" on:click|self on:keypress>x CLOSE</button>
        </div>
        <slot></slot>
    </div>
</div>
{/if}

<style>
    .backdrop {
        height: 100%;
        width: 100%;
        position: fixed;
        background:rgba(0,0,0,0.8);
    }
    .modal{
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        margin:10% auto;
        background-color:white;
    }
    .head-modal{
        display:flex;
        justify-content:space-between;
        align-items:center;
    }
    .close{
        color:red;
        font-size:12px;
        cursor:pointer;
        border: none;
        outline: none;
        background: transparent;
        
    }
    @media only screen and (max-width:600px){
        .modal{
            margin:10px;
        }
    }
    


</style> 