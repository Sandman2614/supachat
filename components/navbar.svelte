<!-- NavBar.svelte -->
<script>
    let isOpen = false;

    function toggleMenu() {
        isOpen = !isOpen;
    }
    import travel from './travel.png';
</script>

<nav class="navbar">
    <div class={travel}>Logo</div>
    <button class="toggle-button" on:click={toggleMenu}>Menu</button>
    <ul class:open={isOpen} class="menu">
        <li><a href="/">Home</a></li>
        <li><a href="Loginscreen.svelte">Contact</a></li>
        <li><a href="/">Login</a></li>
        
    </ul>
</nav>

<style>
    .navbar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #333;
        color: #fff;
        padding: 10px 20px;
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
