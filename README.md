# removal-of-food-waste.git.io
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
