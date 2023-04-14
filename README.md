<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>GitHub Profile</title>
    <style>
      /* CSS styles go here */
      body {
        background-color: #e3e3e3;
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
      }
      
      header {
        background-color: #333333;
        color: white;
        padding: 30px;
      }
      
      .banner {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
      }
      
      h1 {
        font-size: 36px;
        margin: 0;
      }
      
      p {
        font-size: 18px;
        margin: 0;
      }
      
      #dynamic-words {
        font-size: 48px;
        text-align: center;
        margin-top: 50px;
      }
      
      /* Keyframes for dynamic words animation */
      @keyframes animate-words {
        0% {
          opacity: 0;
        }
        25% {
          opacity: 1;
        }
        75% {
          opacity: 1;
        }
        100% {
          opacity: 0;
        }
      }
    </style>
  </head>
  <body>
    <header>
      <div class="banner">
        <h1>George Bahgat</h1>
        <p>Software Engineer</p>
      </div>
    </header>
    
    <div id="dynamic-words">
      <span>Web Developer</span>
      <span>Python Enthusiast</span>
      <span>Coffee Addict</span>
    </div>
    
    <script>
      // JavaScript code goes here
      const words = document.querySelectorAll('#dynamic-words span');
      let currentWord = 0;
      
      function nextWord() {
        words[currentWord].style.animation = 'animate-words 3s ease-in-out';
        words[currentWord].addEventListener('animationend', () => {
          words[currentWord].style.opacity = 0;
          currentWord = (currentWord + 1) % words.length;
          words[currentWord].style.opacity = 1;
          words[currentWord].style.animation = '';
        });
      }
      
      words[currentWord].style.opacity = 1;
      setInterval(nextWord, 3000);
    </script>
  </body>
</html>
