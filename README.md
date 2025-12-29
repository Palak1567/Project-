# appointment scheduler <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Appointment Scheduler</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f5f6fa;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .scheduler-container {
        background-color: #fff;
        padding: 30px 40px;
        border-radius: 10px;
        box-shadow: 0 0 15px rgba(0,0,0,0.2);
        width: 350px;
    }

    h2 {
        text-align: center;
        margin-bottom: 20px;
        color: #2f3640;
    }

    input, select, button {
        width: 100%;
        padding: 10px;
        margin: 10px 0;
        border-radius: 5px;
        border: 1px solid #dcdde1;
        font-size: 16px;
    }

    button {
        background-color: #44bd32;
        color: #fff;
        border: none;
        cursor: pointer;
    }

    button:hover {
        background-color: #4cd137;
    }

    .appointments {
        margin-top: 20px;
    }

    .appointment-item {
        background-color: #f1f2f6;
        padding: 10px;
        margin-bottom: 10px;
        border-radius: 5px;
    }
</style>
</head>
<body>

<div class="scheduler-container">
    <h2>Appointment Scheduler</h2>
    <input type="text" id="name" placeholder="Your Name">
    <input type="date" id="date">
    <input type="time" id="time">
    <button onclick="addAppointment()">Add Appointment</button>

    <div class="appointments" id="appointmentsList">
        <h3>Scheduled Appointments</h3>
    </div>
</div>

<script>
    const appointmentsList = document.getElementById('appointmentsList');

    function addAppointment() {
        const name = document.getElementById('name').value;
        const date = document.getElementById('date').value;
        const time = document.getElementById('time').value;

        if(name === '' || date === '' || time === '') {
            alert('Please fill all fields!');
            return;
        }

        // Create appointment element
        const appointmentItem = document.createElement('div');
        appointmentItem.className = 'appointment-item';
        appointmentItem.innerText = `${name} - ${date} at ${time}`;

        // Add to list
        appointmentsList.appendChild(appointmentItem);

        // Clear inputs
        document.getElementById('name').value = '';
        document.getElementById('date').value = '';
        document.getElementById('time').value = '';
    }
</script>

</body>
</html>