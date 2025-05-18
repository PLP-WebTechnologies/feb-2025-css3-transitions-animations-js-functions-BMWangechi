# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

/* Button animation */
@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}
.animated-btn {
    transition: background-color 0.3s ease, transform 0.3s ease;
}
.animated-btn:hover {
    background-color: lightblue;
    animation: bounce 0.5s ease infinite;
}
/* Image fade-in */
.fade-in {
    opacity: 0;
    transition: opacity 1s ease-in-out;
}
.fade-in.show {
    opacity: 1;
}

// Apply animation on button click
document.getElementById("animateBtn").addEventListener("click", function() {
    this.classList.toggle("animated-btn");
});
// Toggle image fade-in
document.getElementById("showImageBtn").addEventListener("click", function() {
    document.getElementById("animatedImage").classList.toggle("show");
});
// Store user preference for theme color
function savePreference() {
    const color = document.getElementById("themeColor").value;
    localStorage.setItem("preferredColor", color);
    document.body.style.backgroundColor = color; // Apply preference immediately
}
// Retrieve stored preference on page load
window.onload = function() {
    const savedColor = localStorage.getItem("preferredColor");
    if (savedColor) {
        document.body.style.backgroundColor = savedColor;
    }
};
document.getElementById("saveBtn").addEventListener("click", savePreference);

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Elements</title>
    <link rel="stylesheet" href="style2.css">
</head>
<body>
    <button id="animateBtn" class="animated-btn">Click Me for Animation</button>
    
    <button id="showImageBtn">Show Image</button>
    <img id="animatedImage" class="fade-in" src="image.jpg" alt="Animated Image">
    <input type="color" id="themeColor">
    <button id="saveBtn">Save Theme Color</button>
    <script src="script2.js"></script>
</body>
</html>

