<!-- Navbar.svelte -->
<script>
    /** @type {'Home' | 'Login' | 'User' | 'ContactUs'} */
    export let currentScreen;
    import { onMount } from 'svelte';
    import ContactUsScreen from "./contactus.svelte";
    import UserScreen from "./UserScreen.svelte";
    import HomeScreen from "./App.svelte";
    import LoginScreen from './App.svelte';
    let isOpen = false;

    function toggleMenu() {
        isOpen = !isOpen;
    }

    onMount(() => {
        // Close the menu when the user navigates away from the page
        return () => {
            isOpen = false;
        };
    });
</script>

<nav class="navbar">
    <div class="logo">Logo</div>
    <button class="toggle-button" on:click={toggleMenu}>Menu</button>
    <ul class:open={isOpen} class="menu">
        <li><a href="/">Home</a></li>
        <li><a href="Loginscreen.svelte">Login</a></li>
        <li><a href="ContactUsScreen.svelte">Contact Us</a></li>
    </ul>
</nav>

{#if currentScreen === 'Home'}
    <HomeScreen />
{:else if currentScreen === 'Login'}
    <LoginScreen />
{:else if currentScreen === 'User'}
    <UserScreen />
{:else if currentScreen === 'ContactUs'}
    <ContactUsScreen />
{/if}
<style>
    .navbar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #333;
        color: #fff;
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
        color: #fff;
        font-size: 18px;
        transition: color 0.3s ease;
    }

    .menu li a:hover {
        color: #f0f0f0;
    }

    @media screen and (max-width: 768px) {
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
            background-color: #333;
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
