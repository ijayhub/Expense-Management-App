<script>
	import { Route, Router } from 'svelte-navigator'
	import ExpenseComponent from './Pages/ExpenseComponent.svelte';
	import Login from './Pages/Login.svelte';
	import Signup from './Pages/Signup.svelte';
</script>

<main>
	
	<Router>
		<Route path="/">
			<Login/>
		</Route> 
		<Route path="/Signup">
			<Signup/>
		</Route>
		<Route path="/*ExpenseComponent">
			<ExpenseComponent/>
		</Route> 
	</Router>
	
</main>