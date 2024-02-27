<!-- FeaturedAccommodation.svelte -->
<script>
    import alps from './alps.jpg';
    import bali from './bali.jpg';
    import newyork from './newyork.jpg';
  </script>
  
  <style>
    .accommodation-container {
      display: flex;
      justify-content: flex-start;
    }
  
    .accommodation {
      width: 300px;
      height: 400px;
      margin: 5px;
      padding: 20px;
      border: 2px solid #ccc; /* Border for a professional look */
      border-radius: 10px; /* Rounded corners */
      background-color: #f9f9f9; /* Background color */
    }
  
    .accommodation h3 {
      margin-top: 0;
    }
  
    .accommodation p {
      margin-bottom: 10px;
    }
  
    .bali, .newyork, .alps {
      width: 100%;
      height: auto;
      border-radius: 5px; /* Rounded corners for images */
    }
  </style>
  
  <h2>Featured Accommodations</h2>
  
  <div class="accommodation-container">
    <div class="accommodation">
      <h3>Beachfront Villa in Bali</h3>
      <img class="bali" src={bali} alt="Beachfront Villa in Bali">
      <p id="villabali">Relax in luxury at this stunning villa overlooking the ocean.</p>
      <p>From R29990</p>
    </div>
  
    <div class="accommodation">
      <h3>Mountain Lodge Swiss Alps</h3>
      <img class="alps" src={alps} alt="Mountain Lodge in the Swiss Alps">
      <p id="Swiss">Experience the beauty of the Swiss Alps with a cozy stay in this mountain lodge.</p>
      <p>From R42990</p>
    </div>
  
    <div class="accommodation">
      <h3>City Apartment in New York</h3>
      <img class="newyork" src={newyork} alt="City Apartment in New York">
      <p id="Explore">Explore the vibrant city life of New York from the comfort of this stylish apartment.</p>
      <p>From R27990</p>
    </div>
  </div>
  