<script>
  import { Link } from 'svelte-navigator'
  import Button from '../shared/Button.svelte';
  import ExpenseComponenet from '../Pages/ExpenseComponent.svelte'
  let email=""
  let password=""
  // $:isSucessful=alert('login in')
</script>

<form>
  <div class="input-container">
    <div  class="login-title">
      <h4>EM LOGIN</h4>
    </div>
    <label for="email">Email</label>
    <input type="email" id="email" required bind:value={email} />
    <label for="password">Password</label>
    <input type="password" id="password" required bind:value={password} />
    <Link to="/ExpenseComponenet">
      <Button>Login</Button>
    </Link>
    <div class="not-registered">
      <small>Not yet registered?</small>
      <Link to="/Signup"><small class="login">Signup</small></Link>
    </div>
  </div>
</form>
    <style>
    form{
      display:flex;
      flex-direction:column;
      padding:15px;
      align-items:center;
      justify-content:center;
      height:100vh;
    }
    .input-container{
      box-shadow: 2px 2px 2px rgba(0,0,0,0.2);
      border:2px solid green;
      max-width:500px;
      padding:20px;
      background:white;
    }
    .login-title{
      text-align: center;
      color:green;
      border:none;
      outline: none;
    }
    label{
      text-align:left;
      font-size:20px;
      opacity: 0.6;
      font-size:12px;
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
    
    input:focus{
      border: 1px solid black;
    }
    .not-registered{
      margin:15px 0;
      text-align: center;
    }
    .login{
      color:green;
      font-weight: 700;
    }
</style> 