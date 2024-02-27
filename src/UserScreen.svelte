<script lang="ts">
  import { currentUser, supabase } from "./lib/supabase";
  import { writable } from 'svelte/store';
  

  
  let userEmail = writable<string | undefined>(undefined);

  
  currentUser.subscribe(value => {
    
    userEmail.set(value ? value.email : undefined);
  });

 
  async function handleSignOut() {
    const { error } = await supabase.auth.signOut();

    if (error) {
      console.error("Error signing out:", error.message);
    } else {
      console.log("Sign out successful");
      // Redirect to the login screen after signing out
      window.location.href = '/login';
    }
  }
</script>

<div class="flex flex-col items-center justify-center w-full py-20">
  <div class="container">
    {#if $currentUser}
      <div class="user-info">
        <h2>Welcome, {$userEmail}!</h2>
        <p>You are currently logged in.</p>
        <p>Feel free to explore the app!</p>
      </div>
      <button class="sign-out-button" on:click={handleSignOut}>Sign Out</button>
    {:else}
      <p>User not logged in</p>
    {/if}
  </div>
</div>
<style>
  /* Style for the container */
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px;
  }

  /* Style for the user information */
  .user-info {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 20px;
    margin-bottom: 20px;
    width: 300px;
    text-align: center;
  }

  /* Style for the sign-out button */
  .sign-out-button {
    background-color: #ff6347;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 10px 20px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .sign-out-button:hover {
    background-color: #e74c3c;
  }
</style>