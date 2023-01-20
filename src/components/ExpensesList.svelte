<script>
    import ExpenseDetails from "./ExpenseDetails.svelte";
    import { fade } from 'svelte/transition'
    import {flip} from 'svelte/animate'

    export let expenses=[]
    export let handleDelete
</script>

<section>
    <h2>Expenses List</h2>
    <ul >
        {#each expenses as expense (expense.id)}
        <div out:fade|local>
            <ExpenseDetails {...expense} {handleDelete}/> 
        </div>
            
            {:else}
                <p class="no-expense">Oops...No More Expenses</p>
        {/each}
    </ul>
</section>

<style>
    h2{
		margin-top:50px;
		color: #009579;
		text-shadow:4px 4px 4px rgba(0,0,0,0.1);
	}
    .no-expense {
        margin-top:20px;
        color:#009579;
        text-align: center;
        font-size:20px;
    }
</style>