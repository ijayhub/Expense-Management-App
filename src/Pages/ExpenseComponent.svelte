<script>
	import { Link } from 'svelte-navigator';

	// components
	import ExpensesList from '../components/ExpensesList.svelte';
	import Header from "../components/Header.svelte";
	import Total from "../components/Total.svelte"

	// data
	import expensesData from '../expenses'

	// reactive value
	$:total=expenses.reduce((previous, current )=>{
		return  previous += current.amount
	},0)
	// variable
	let expenses = [...expensesData]
	let item=expenses
	localStorage.setItem("expenses",item)
	// console.log(expenses)
	let name = ""
	let amount = ""
	export let showModal = false

	// function for a delete handler
	const handleDelete=(id) => {
		expenses=expenses.filter((item)=>item.id !== id)
	}
	 // function to clear all the expenses
	const clearExpenses = () => {
		expenses=[]
	}
	
	  // function to addExpenses
    const addExpenses = (e) => {
        const expense = e.detail;
        expenses = [expense,...expenses];
        showModal = false;
	}
</script>

<Header on:addExpense={addExpenses}/>

<main>
	<Total {total}/>
	<ExpensesList  {expenses} {handleDelete} />
	<div>
        <button type="button" class="btn-expense" on:click={clearExpenses}>Clear Expenses</button>
	</div>
</main>
<Link to="/">
	<button class="backHome-btn">Back Home</button>
</Link>
<style>
	main{
		max-width: 500px;
		margin: 0 auto;
	}
	.btn-expense{
        padding:6px;
        border-radius: 5px;
        width:100%;
        background-color: #009579;
        color:white;
        letter-spacing:3px;
        text-transform: uppercase;
        margin-top:20px;
        border:none;
        box-shadow: 3px 3px 3px rgba(0,0,0,0.6);
        font-size:12px;
        outline: none;
    }
    .btn-expense:hover{
        background-color:white;
        color:#009579;
        border:1px solid #009579;
    }
	.backHome-btn{
		padding:8px;
        border-radius: 5px;
        background-color: #009579;
        color:white;
        letter-spacing:3px;
        text-transform: uppercase;
        margin:30px;
        border:none;
        box-shadow: 3px 3px 3px rgba(0,0,0,0.6);
        font-size:12px;
        outline: none;
	}
	@media only screen and (max-width:600px){
		main{
			margin:0 10px;
		}
	}
</style>