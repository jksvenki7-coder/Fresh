# Fresh
Freshitems
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Home Website</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f5f9ff;
      text-align: center;
    }

    header {
      background: #0077b6;
      color: white;
      padding: 15px;
    }

    nav {
      display: flex;
      justify-content: space-around;
      background: #023e8a;
      padding: 10px 0;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      padding: 8px 12px;
      border-radius: 5px;
    }

    nav a:hover {
      background: #0077b6;
    }

    section {
      padding: 30px;
    }

    form {
      background: white;
      max-width: 400px;
      margin: auto;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0px 2px 6px rgba(0,0,0,0.2);
    }

    input, textarea, button {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 16px;
    }

    button {
      background: #0077b6;
      color: white;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background: #023e8a;
    }
  </style>
</head>
<body>
  <header>
    <h1>My Home Website</h1>
  </header>

  <nav>
    <a href="#">Home Page</a>
    <a href="#">Contact Us</a>
    <a href="#">Camera</a>
    <a href="#">Orders</a>
    <a href="#">Profile</a>
  </nav>

  <section>
    <h2>Place Your Order</h2>
    <form id="orderForm">
      <input type="text" id="name" placeholder="Enter your name" required>
      <input type="tel" id="phone" placeholder="Enter your phone number" required><!DOCTYPE html>
<html>
<head>
    <title>Delivery Place Selection</title>
    <style>
        #map {
            height: 400px;
            width: 100%;
            margin-top: 10px;
        }
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            font-size: 16px;
            padding: 8px;
        }
    </style>
</head>
<body>
    <h2>Select Delivery Place</h2>
    <input id="address" type="text" placeholder="Enter your delivery address" style="width: 300px;">
    <button onclick="codeAddress()">Show on Map</button>

    <div id="map"></div>

    <script>
        let map;
        let geocoder;
        let marker;

        function initMap() {
            const defaultLocation = { lat: 40.7128, lng: -74.0060 }; // Default: New York City

            map = new google.maps.Map(document.getElementById('map'), {
                zoom: 12,
                center: defaultLocation
            });

            geocoder = new google.maps.Geocoder();
        }

        function codeAddress() {
            const address = document.getElementById('address').value;
            geocoder.geocode({ 'address': address }, function(results, status) {
                if (status === 'OK') {
                    map.setCenter(results[0].geometry.location);

                    if (marker) {
                        marker.setMap(null);
                    }

                    marker = new google.maps.Marker({
                        map: map,
                        position: results[0].geometry.location
                    });
                } else {
                    alert('Geocode was not successful for the following reason: ' + status);
                }
            });
        }
    </script>

    <script async defer 
      src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
    </script>
</body>
</html>
      <textarea id="order" rows="3" placeholder="Enter your order details" required></textarea>
      <button type="submit">Send via WhatsApp</button>
    </form>
  </section>

  <script>
    document.getElementById("orderForm").addEventListener("submit", function(e){
      e.preventDefault();
      
      let name = document.getElementById("name").value;
      let phone = document.getElementById("phone").value;
      let order = document.getElementById("order").value;

      let message = `Hello, my name is ${name}. My phone number is ${phone}. I want to order: ${order}`;
      let whatsappURL = `https://wa.me/918977143043?text=${encodeURIComponent(message)}`;
      
      window.open(whatsappURL, "_blank");
    });
  </script>

</body>
</html>
