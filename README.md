<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is a simple HTML structure.</p>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Webpage</title>
</head>
<body>
    <h1>Welcome to My Site</h1>
    <p>This is a basic HTML structure.</p>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <style>
        body { background: #f0f2f5; font-family: sans-serif; display: flex; height: 100vh; justify-content: center; align-items: center; margin: 0; }
        
        /* Fade-in Animation */
        .card { 
            background: white; padding: 40px; border-radius: 15px; text-align: center; box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            animation: fadeIn 1.5s ease-in;
        }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

        /* Button Hover Effect */
        button {
            background: #007bff; color: white; border: none; padding: 12px 25px; border-radius: 5px; cursor: pointer;
            transition: transform 0.3s, background 0.3s;
        }

        button:hover { background: #0056b3; transform: scale(1.1); }
    </style>
</head>
<body>
    <div class="card">
        <h1>Cloud Project</h1>
        <p>This page loaded with a smooth fade-in effect.</p>
        <button>Hover Over Me</button>
    </div>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <style>
        /* Moving Gradient Background */
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', sans-serif;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Glassmorphism Card */
        .glass-card {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 50px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            text-align: center;
            color: white;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
        }

        button {
            background: white;
            color: #e73c7e;
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover { transform: translateY(-5px); box-shadow: 0 5px 15px rgba(0,0,0,0.3); }
    </style>
</head>
<body>
    <div class="glass-card">
        <h1>Vibrant Design</h1>
        <p>This background shifts colors automatically!</p>
        <button>Explore More</button>
    </div>
</body>
</html>
