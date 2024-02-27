
<script>
 
</script>

<div class="container">
    <h1>Contact Us</h1>
    <p>Feel free to reach out to us using the following methods:</p>
    <ul class="contact-info">
        <li><span>Email:</span> <a href="mailto:sales@bookit.com">sales@bookit.com</a></li>
        <li><span>Phone:</span> +27 21 123 4567</li> 
        <li><span>Address:</span> 123 Main Street, Cape Town, South Africa</li>
    </ul>
    <div class="map">
        <!-- svelte-ignore a11y-missing-attribute -->
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d847643.4406694226!2d17.9966159377238!3d-33.91264070886204!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x1dcc500f8826eed7%3A0x687fe1fc2828aa87!2sCape%20Town!5e0!3m2!1sen!2sza!4v1709065188322!5m2!1sen!2sza" width="600" height="450" style="border:0;"  loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        <iframe src="https://maps.app.goo.gl/YSV9xEZwVP5RtqDF7" width="100%" height="450" frameborder="0" style="border:0;" allowfullscreen title="Google Maps"></iframe>
    </div>
</div>

<style>
  .container {
        padding: 20px;
        background-color: #f9f9f9;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        max-width: 800px;
        margin: 0 auto;
    }

    h1 {
        font-size: 28px;
        font-weight: bold;
        margin-bottom: 20px;
    }

    p {
        font-size: 18px;
        margin-bottom: 20px;
    }

    .contact-info {
        list-style: none;
        padding: 0;
        margin: 0;
    }

    .contact-info li {
        margin-bottom: 15px;
    }

    .contact-info li span {
        font-weight: bold;
        margin-right: 10px;
    }

    .contact-info li a {
        color: #007bff;
        text-decoration: none;
    }

    .contact-info li a:hover {
        text-decoration: underline;
    }

    .map {
        margin-top: 20px;
    }

    .map iframe {
        width: 100%;
        height: 450px;
        border-radius: 10px;
    }
</style>
