

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spoed Massage - Book Your Session</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #6ab3b3;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .container {
            width: 80%;
            margin: 0 auto;
            padding: 20px;
        }
        .form-container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .form-group {
            margin-bottom: 15px;
        }
        .form-group label {
            display: block;
            margin-bottom: 5px;
        }
        .form-group input, .form-group select, .form-group button {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .form-group button {
            background-color: #6ab3b3;
            color: white;
            border: none;
            cursor: pointer;
        }
        .form-group button:hover {
            background-color: #579797;
        }
        .images {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
        .images img {
            width: 48%;
            margin-bottom: 10px;
            border-radius: 8px;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: #6ab3b3;
            color: white;
        }
    </style>
</head>
<body>

<header>
    <h1>Spoed Massage</h1>
    <p>Book Your Massage Session Online</p>
</header>

<div class="container">
    <div class="form-container">
        <h2>Book a 60-minute Massage Session</h2>
        <form id="booking-form">
            <div class="form-group">
                <label for="name">Full Name:</label>
                <input type="text" id="name" name="name" required>
            </div>
            <div class="form-group">
                <label for="email">Email Address:</label>
                <input type="email" id="email" name="email" required>
            </div>
            <div class="form-group">
                <label for="date">Select Date:</label>
                <input type="date" id="date" name="date" required>
            </div>
            <div class="form-group">
                <label for="time">Select Time:</label>
                <select id="time" name="time" required>
                    <option value="09:00">09:00</option>
                    <option value="10:00">10:00</option>
                    <option value="11:00">11:00</option>
                    <option value="12:00">12:00</option>
                    <option value="13:00">13:00</option>
                    <option value="14:00">14:00</option>
                    <option value="15:00">15:00</option>
                </select>
            </div>
            <div class="form-group">
                <button type="submit">Book Now</button>
            </div>
        </form>
    </div>

    <div class="images">
        <img src="sport-massage.jpg" alt="Sport Massage">
        <img src="medical-taping.jpg" alt="Medical Taping">
        <img src="triggerpoints-massage.jpg" alt="Triggerpoints Massage">
        <img src="relax-massage.jpg" alt="Relax Massage">
    </div>
</div>

<footer>
    <p>© 2024 Spoed Massage. All rights reserved.</p>
</footer>

<script>
    document.getElementById('booking-form').addEventListener('submit', function(event) {
        event.preventDefault();
        const name = document.getElementById('name').value;
        const email = document.getElementById('email').value;
        const date = document.getElementById('date').value;
        const time = document.getElementById('time').value;

        const data = {
            name: name,
            email: email,
            date: date,
            time: time
        };

        fetch('https://formspree.io/f/your-form-id', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(data)
        }).then(response => {
            if (response.ok) {
                alert('Booking confirmed. You will receive an email notification.');
                document.getElementById('booking-form').reset();
            } else {
                alert('There was an error with your booking. Please try again.');
            }
        }).catch(error => {
            console.error('Error:', error);
            alert('There was an error with your booking. Please try again.');
        });
    });
</script>

</body>
</html>
