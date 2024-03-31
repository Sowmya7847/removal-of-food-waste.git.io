<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3Rs of Food Waste - Reduce, Rescue, Redistribute</title>
    <style>
        /* CSS styles here */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #C2D69B; /* Olive Green */
            color: #333; /* Dark gray */
        }
        header {
            background-color: #556B2F; /* Dark Olive Green */
            color: #fff; /* White */
            text-align: center;
            padding: 20px 0;
        }
        nav {
            background-color: #6B8E23; /* Olive Drab */
            color: #333; /* Dark gray */
            text-align: center;
            padding: 10px 0;
        }
        nav a {
            color: #333; /* Dark gray */
            text-decoration: none;
            margin: 0 10px;
        }
        section {
            padding: 20px;
        }
        h2 {
            color: #556B2F; /* Dark Olive Green */
            cursor: pointer; /* Add cursor pointer to indicate interactivity */
        }
        p {
            color: #666; /* Medium gray */
        }
        footer {
            background-color: #556B2F; /* Dark Olive Green */
            color: #fff; /* White */
            text-align: center;
            padding: 20px 0;
        }
        .btn {
            display: inline-block;
            padding: 8px 16px;
            background-color: #6B8E23; /* Olive Drab */
            color: #fff; /* White */
            border: none;
            border-radius: 4px;
            cursor: pointer;
            text-decoration: none;
            transition: background-color 0.3s ease;
        }
        .btn:hover {
            background-color: #556B2F; /* Darker Olive Green on hover */
        }
        .form-input {
            margin-bottom: 10px;
            width: 100%;
            padding: 8px;
            border-radius: 4px;
            border: 1px solid #ccc; /* Light gray */
            box-sizing: border-box;
        }
        .recipe {
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-bottom: 20px;
            padding: 10px;
        }
        .recipe h3 {
            color: #556B2F; /* Dark Olive Green */
            margin-top: 0;
        }
        .recipe img {
            max-width: 100%;
            height: auto;
            border-radius: 4px;
            margin-bottom: 10px;
        }
        .community-post {
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-bottom: 20px;
            padding: 10px;
        }
        .community-post h3 {
            color: #556B2F; /* Dark Olive Green */
            margin-top: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>3Rs of Food Waste - Reduce, Rescue, Redistribute</h1>
    </header>
    <nav>
        <a href="#problem">The Problem</a>
        <a href="#reduce">Reduce</a>
        <a href="#rescue">Rescue</a>
        <a href="#redistribute">Redistribute</a>
        <a href="#impact">Impact Stories</a>
        <a href="#share">Share Your Story</a>
        <a href="#tips">Tips and Resources</a>
        <a href="#partnerships">Partnerships</a>
    </nav>
    <section id="problem">
        <h2 onclick="toggleContent('problem')">The Problem</h2>
        <p>Description of the impact of food waste and why it's important to address it.</p>
        <p>Food waste contributes to greenhouse gas emissions.</p>
        <p>Wasted food means wasted resources used in production.</p>
        <p>It strains food systems and exacerbates hunger and poverty.</p>
        <p>Reducing food waste can lead to significant environmental benefits.</p>
    </section>
    <section id="reduce">
        <h2 onclick="toggleContent('reduce')">Reduce</h2>
        <p>Information on reducing food waste through smarter shopping, meal planning, and portion control.</p>
        <p>Buying only what you need reduces the likelihood of food going bad.</p>
        <p>Meal planning helps in utilizing ingredients efficiently.</p>
        <p>Portion control prevents excess food from being cooked.</p>
        <p>Awareness about expiry dates aids in consuming food before it spoils.</p>
    </section>
    <section id="rescue">
        <h2 onclick="toggleContent('rescue')">Rescue</h2>
        <p>Details about rescuing surplus food from going to waste and redirecting it to those in need.</p>
        <p>Food rescue involves collecting excess food from various sources.</p>
        <p>Redirecting surplus food to shelters and food banks helps feed the hungry.</p>
        <p>Collaborating with restaurants and supermarkets reduces food waste at the source.</p>
        <p>Food rescue initiatives require coordination and logistics.</p>
    </section>
    <section id="redistribute">
        <h2 onclick="toggleContent('redistribute')">Redistribute</h2>
        <p>Methods for redistributing excess food to community organizations, food banks, and shelters.</p>
        <p>Community organizations play a vital role in redistributing surplus food.</p>
        <p>Food banks distribute food to individuals and families in need.</p>
        <p>Collaborating with local shelters ensures food reaches those who need it most.</p>
        <p>Redistributing food reduces waste and helps alleviate food insecurity.</p>
    </section>
    <section id="impact">
        <h2 onclick="toggleContent('impact')">Impact Stories</h2>
        <div id="impact-stories">
            <!-- Stories will be loaded dynamically -->
        </div>
    </section>
    <section id="share">
        <h2>Share Your Story</h2>
        <form id="story-form" action="submit_story.php" method="post">
            <input type="text" id="name" name="name" class="form-input" placeholder="Your Name" required><br>
            <input type="email" id="email" name="email" class="form-input" placeholder="Your Email" required><br>
            <textarea id="story" name="story" class="form-input" rows="4" placeholder="Your Story" required></textarea><br>
            <button type="submit" class="btn">Submit</button>
        </form>
    </section>
    <section id="tips">
        <h2>Tips and Resources</h2>
        <p>Include tips and resources for reducing food waste here...</p>
    </section>
    <footer>
        <p>&copy; 2024 3Rs of Food Waste. All rights reserved.</p>
    </footer>
    <script>
        // JavaScript code here
        function toggleContent(sectionId) {
            var section = document.getElementById(sectionId);
            var isVisible = section.style.display === 'none' || section.style.display === '';
            section.style.display = isVisible ? 'block' : 'none';
        }
    </script>
</body>
</html>
<?php
// Check if form is submitted
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Get form data
    $name = $_POST['name'];
    $email = $_POST['email'];
    $story = $_POST['story'];

    // Email content
    $to = 'jeediguntasowmya@gmail.com'; // Destination email address
    $subject = 'New Story Submission';
    $message = "Name: $name\n\nEmail: $email\n\nStory: $story";

    // Send email
    if (mail($to, $subject, $message)) {
        echo "Your story has been submitted successfully!";
    } else {
        echo "Failed to submit your story. Please try again later.";
    }
}
?>
