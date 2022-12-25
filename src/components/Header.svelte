<script>
    import BudgetForm from "./BudgetForm.svelte";
    import Modal from "./Modal.svelte";
    
    // modal toggle
        let showModal=false;
        const toggleModal=()=>{
        showModal=!showModal;
    }
</script>
<header>
    <Modal {showModal} on:click={toggleModal}  >
        <BudgetForm  on:addExpense/>
    </Modal>
    <div class="calculator-container">
        <span class="budget">Expense Tracker App</span>
        <div>
            <button class="expense" on:click={toggleModal}>
                <img src="../../img/plus-square (2).svg" alt="plus"/>
                <span class="span-expense">Add Expense</span>
            </button>
        </div>
    </div>
</header>

<style>
    header{
        background-color: #009579;
        box-shadow: 4px 4px 4px rgba(0,0,0,0.5);
    }
    .calculator-container{
        display:flex;
        justify-content: space-evenly;
        align-items: center;
        font-size: 20px;
        padding: 20px;

    }
    .budget{
        color: #fff;
        font-family: 'Catamaran', sans-serif;
        font-weight:700
    }
    .expense{
        display:flex;
        justify-content:center;
        align-items: center;
        background-color: transparent;
        border:none;
        cursor:pointer;
    }
    .expense:hover{
        color:#a7a5ca;
    }
    .span-expense{
        font-size: 20px;
        font-family: Arial, Helvetica, sans-serif;
    }
    @media only screen and (max-width:600px){
        .calculator-container, .span-expense{
            font-size: 16px;
        }
        
    }
</style>