<script lang="ts">
	import HomeScreen from "./Home.svelte";
	import LoginScreen from "./LoginScreen.svelte";
	import UserScreen from "./UserScreen.svelte";
	import ContactUsScreen from "./contactus.svelte";
  import Header from "../components/header.svelte";
	let isOpen = false;
	let currentScreen = 'Home';

	function toggleMenu() {
		isOpen = !isOpen;
	}

	function navigateTo(screen: string) {
		currentScreen = screen;
		isOpen = false; // Close the menu after navigation
	}
</script>

<Header/>


 <nav class="navbar">
  <div class="logo"></div>
  <button class="toggle-button" on:click={toggleMenu}>Menu</button>
  <ul class:open={isOpen} class="menu">
    <li><a href="./Home.svelte" on:click|preventDefault={() => navigateTo('Home')}>Home</a></li>
    <li><a href="./LoginScreen.svelte" on:click|preventDefault={() => navigateTo('Login')}>Login</a></li>
    <li><a href="./UserScreen.svelte" on:click|preventDefault={() => navigateTo('User')}>User</a></li>
    <li><a href="./contactus.svelte" on:click|preventDefault={() => navigateTo('ContactUs')}>Contact Us</a></li>
</ul>
</nav>

<main>
  {#if currentScreen === 'Home'}
      <HomeScreen />
  {:else if currentScreen === 'Login'}
      <LoginScreen />
  {:else if currentScreen === 'User'}
      <UserScreen />
  {:else if currentScreen === 'ContactUs'}
      <ContactUsScreen />
  {/if}



</main>
  
<style>
  	.navbar {
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #213547;
		color: #ffffff;
		padding: 10px 20px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	}

	.logo {
		font-size: 24px;
		font-weight: bold;
	}

	.toggle-button {
		display: none;
		background-color: transparent;
		color: inherit;
		border: none;
		cursor: pointer;
		font-size: 18px;
	}

	.menu {
		list-style-type: none;
		display: flex;
		padding: 0;
		margin: 0;
	}

	.menu li {
		margin-right: 20px;
	}

	.menu li:last-child {
		margin-right: 0;
	}

	.menu li a {
		text-decoration: none;
		color: #ffffff;
		font-size: 18px;
		transition: color 0.3s ease;
	}

	.menu li a:hover {
		color: #f0f0f0;
	}

	@media screen and (max-width: 1200px) {
		.toggle-button {
			display: block;
		}

		.menu {
			display: none;
			flex-direction: column;
			position: absolute;
			top: 60px;
			left: 0;
			width: 100%;
			background-color: #213547;
			padding: 10px 0;
			z-index: 1;
		}

		.menu.open {
			display: flex;
		}

		.menu li {
			margin-right: 0;
			margin-bottom: 10px;
		}
	}
</style>


 