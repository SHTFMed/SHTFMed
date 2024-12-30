<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SHTF Medical Skills</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #3b3b3b; /* OD green background */
            color: #fff;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #6b5b3a; /* Coyote tan header */
            padding: 20px;
            text-align: center;
        }
        header h1 {
            margin: 0;
            color: #fff;
        }
        section {
            padding: 20px;
            margin: 20px;
            background-color: #4b4b4b; /* Slightly lighter OD green */
            border-radius: 10px;
        }
        h2 {
            color: #e0c090; /* Coyote tan for headings */
        }
        .button {
            background-color: #6b5b3a; /* Coyote tan button */
            color: #fff;
            padding: 10px 20px;
            text-align: center;
            display: inline-block;
            border-radius: 5px;
            text-decoration: none;
        }
        .button:hover {
            background-color: #5a4a2a;
        }
        footer {
            background-color: #2b2b2b;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
        label, input, select, textarea {
            display: block;
            margin-bottom: 10px;
            width: 100%;
        }
    </style>
</head>
<body>

<header>
    <h1>SHTF Medical Skills</h1>
</header>

<section>
    <h2>Mission Statement</h2>
    <p>At SHTF Medical Skills, our mission is to provide high-quality, practical training in tactical combat casualty care and basic life support, equipping individuals with the skills needed to save lives in critical situations.</p>
</section>

<section>
    <h2>How to Book a Course</h2>
    <p>Booking a course with us is simple. Just fill in the form below:</p>
    <form id="bookingForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="course">Course:</label>
        <select id="course" name="course" required>
            <option value="tccc">Tactical Combat Casualty Care (TCCC)</option>
            <option value="bls">Basic Life Support (BLS)</option>
        </select>

        <label for="date">Preferred Date:</label>
        <input type="date" id="date" name="date" required>

        <button type="submit" class="button">Book Now</button>
    </form>
    <p>For any questions or assistance, please <a href="mailto:info@shtfmedicalskills.com" class="button">Contact Us</a>.</p>
</section>

<section>
    <h2>About Our Courses</h2>
    <h3>Tactical Combat Casualty Care (TCCC)</h3>
    <p>This course is designed for individuals who need to be prepared for high-stress, emergency situations. This course covers essential topics such as:</p>
    <ul>
        <li>Bleeding control</li>
        <li>Airway management</li>
        <li>Chest injuries</li>
        <li>Shock management</li>
        <li>Medical evacuation techniques</li>
    </ul>
    <h3>Basic Life Support (BLS)</h3>
    <p>The Basic Life Support course is intended for healthcare professionals and other personnel who need to know how to perform CPR and other basic cardiovascular life support skills in a wide variety of in-facility and prehospital settings.</p>
    <ul>
        <li>High-quality CPR for adults, children, and infants</li>
        <li>Chain of Survival</li>
        <li>Use of an AED</li>
        <li>Effective ventilations using a barrier device</li>
        <li>Relief of choking</li>
    </ul>
</section>

<footer>
    <p>&copy; 2024 SHTF Medical Skills. All rights reserved.</p>
</footer>

<script>
    document.getElementById('bookingForm').addEventListener('submit', function(event) {
        event.preventDefault();
        const name = document.getElementById('name').value;
        const email = document.getElementById('email').value;
        const course = document.getElementById('course').value;
        const date = document.getElementById('date').value;
        
        // Example of handling form submission
        fetch("https://formspree.io/f/YOUR_FORM_ID", {
            method: "POST",
            headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                name: name,
                email: email,
                course: course,
                date: date
            })
        }).then(response => {
            if (response.ok) {
                alert('Your booking request has been submitted.');
                document.getElementById('bookingForm').reset();
            } else {
                alert('There was a problem with your submission. Please try again.');
            }
        }).catch(error => {
            console.error('Error:', error);
            alert('There was a problem with your submission. Please try again.');
        });
    });
</script>

</body>
</html>
