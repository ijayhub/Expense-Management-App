<script>
    import { Link } from 'svelte-navigator'
    import Button from '../shared/Button.svelte';
    let name="";
    let email ="";
    let password ="";
</script>

<form>
    <div class="input-container">
        <div class="signup-title">
            <h4>EM Register</h4>
        </div>
        <label for="name">Name</label>
        <input type="text" id="name" required bind:value={name} />
        <label for="email">Email</label>
        <input type="email" id="email" required bind:value={email} />
        <label for="password">Password</label>
        <input type="password" id="password" required bind:value={password} />
        <Button>Register</Button>
        <div class="registered">
            <small>Already registered?</small>
            <Link to="/"><small class="signup">Login</small></Link>
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
    .signup-title{
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
    .registered{
        margin:15px 0;
        text-align: center;
    }
    .signup{
        color:green;
    }
</style> 