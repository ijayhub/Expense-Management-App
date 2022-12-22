<script>
    import{createEventDispatcher} from 'svelte'
    import {slide}from 'svelte/transition'

    let dispatch = createEventDispatcher()
    // componenet
    import Button from "../shared/Button.svelte";
    
    let name=''
    let amount=null
    let showModal = false
    
     // validate the form
        $:isEmpty=!name||!amount
    
    const handleSubmit=(e)=>{
        let expense = {
            id:Math.random(),
            name, 
            amount
        };
        dispatch('addExpense', expense)
    }
</script>


<form class="form" on:submit|preventDefault={handleSubmit} in:slide >
    <div>
        <label for="Name">Name</label>
        <input type="text" id="Name" bind:value={name} />
    </div>
    <div>
        <label for="Amount">Amount</label>
        <input type="number" id="Amount" bind:value={amount}/>
    </div>
    {#if isEmpty}
    <div class="error">Please fill out all form fields</div>
    {/if}
    
    <Button type="submit" isDisabled={isEmpty}>Add Expense</Button>
</form>

<style>
    .form{
        display:flex;
        flex-direction:column;
        padding:15px;
    }
    label{
        text-align:left;
    }
    input{
        width:100%;
        padding:8px;
        border-bottom: 1px solid grey;
        border-top: none;
        border-left: none;
        border-right: none;
        margin: 10px 0;
    }
    label{
        opacity: 0.6;
        font-size:12px;
        
    }
    input:focus{
        border: 1px solid black;
        
    }
    .error{
        color:red;
        display: block;
        font-size:12px;
        margin: 12px 0;
        text-align: center;
    }
</style> 