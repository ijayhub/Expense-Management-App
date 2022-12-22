<script>
    export let handleDelete
    export let id;
    export let name = ""
    export let amount = 0; 

    let showAmount = false
    const handleShowAmount=()=>{
        showAmount = !showAmount;
    }
    
</script>

<section >
        <div class="single-expense">
            <div class="expense-info">
                <h2 class="expense-title">
                    {name}
                    <button type="button" on:click={handleShowAmount}>
                        <img src="/img/caret.svg" alt="" />
                    </button>
                </h2>
                {#if showAmount}
                    <h4 class="expense-amount">Amount: {amount}</h4>
                {/if}
            </div>
            <div class="expense-button">
                <button class="delete-btn" on:click="{()=>handleDelete(id)}">
                    <img src="/img/trash (1).svg" alt="delete"/>
                </button>
            </div>
    </div>
</section>

<style>
    .single-expense{
        display:flex;
        justify-content:space-between;
        align-items:center;
        background-color:white;
        box-shadow:3px 3px 3px rgba(0,0,0,0.6);
        margin-top:10px;
        padding:15px;
        border-radius: 5px;
        font-weight: 100;
    }
    .expense-title{
        margin-bottom: 10px;
    }
    .expense-amount{
        color:#009579;
    }
    button{
        background: none;
        border:none;
        outline:none;
        cursor:pointer;
    }
    
</style>