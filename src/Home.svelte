<script lang="ts">
   
	  import Header from '../components/header.svelte';
    import LoginScreen from "./LoginScreen.svelte";
    import { currentUser } from "./lib/supabase";
    import UserScreen from "./UserScreen.svelte";
    import Navbar from '../components/navbar.svelte';
    import FeaturedAccommodation from '../components/featuredaccommodation.svelte';
  </script>
<style>
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

h2 {
    font-size: 24px;
    margin-bottom: 10px;
}

p {
    font-size: 16px;
    margin-bottom: 20px;
}

.search-form {
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.form-group {
    margin-bottom: 20px;
}

label {
    font-weight: bold;
}

input[type="text"],
input[type="date"] {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
}

.search-button {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

.search-button:hover {
    background-color: #0056b3;
}

</style>

 <main>
  <div class="container">
    <h2>Welcome to Book it!</h2>
    <p>Find your perfect accommodation and start your adventure!</p>
    <form action="search.php" method="get" class="search-form">
        <div class="form-group">
            <label for="location">Location:</label>
            <input type="text" id="location" name="location" placeholder="Enter location" required>
        </div>
        <div class="form-group">
            <label for="check-in">Check-in date:</label>
            <input type="date" id="check-in" name="check-in" required>
        </div>
        <div class="form-group">
            <label for="check-out">Check-out date:</label>
            <input type="date" id="check-out" name="check-out" required>
        </div>
        <button type="submit" class="search-button">Search</button>
    </form>


      <FeaturedAccommodation/>
  </div>
</main>
 