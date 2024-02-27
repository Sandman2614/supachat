<!-- Header.svelte -->
<script>
  function redirectToAccount() {
    window.location.href = 'account.html';
  }
  import logo from './logo.png';

</script>

<header class="header-container">
  <img class="logo" src={logo} alt="Logo">
  <a class="account-link" href="account.html" on:click|preventDefault={redirectToAccount}>
    
  </a>
</header>

<style>
  .header-container {
      display: flex;
      justify-content: center; /* Horizontally center the content */
      align-items: center; /* Vertically center the content */
      background-color: #2ecc71;
      color: #fff;
      padding: 10px 20px;
      text-align: center;
      position: relative;
      width: 1200px;
  }


  .logo {
      border-radius: 45%;
      width: 200px;
      height: 200px;
  }
</style>
