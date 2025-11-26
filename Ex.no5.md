# Ex05 Image Carousel
## Date: 25/11/2025

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
## App.jsx
```
import React, { useState } from 'react';
import './App.css';

const images = [
  'Cricket1.jpg',
  'Cricket2.webp'
];

function App() {
  const [index, setIndex] = useState(0);

  const showPrevious = () => {
    setIndex((prevIndex) => (prevIndex === 0 ? images.length - 1 : prevIndex - 1));
  };

  const showNext = () => {
    setIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  };

  return (
    <div className="app">
      <h1 className="title">Cricket🏏</h1>
      <div className="carousel">
        <img src={images[index]} alt="Aniverse" className="carousel-image" />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>

      {/* Footer */}
      <div className="footer">
        &copy; DINAGARAN JOHNY S ||  212223220020
       </div>
    </div>
  );
}

export default App;
```
## App.css
```
body {
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(to bottom right, #dbeafe, #e9d5ff);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.app {
  background: white;
  border-radius: 20px;
  padding: 40px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
  text-align: center;
  width: 700px;
  max-width: 90%;
}

.title {
  font-size: 2.5rem;
  color: #4c1d95;
  font-weight: 700;
  margin-bottom: 30px;
}

.carousel {
  position: relative;
  width: 100%;
  height: 400px;
  overflow: hidden;
  border-radius: 15px;
  margin-bottom: 20px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
}

.carousel-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 15px;
  transition: opacity 0.6s ease-in-out, transform 0.3s ease-in-out;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 25px;
}

button {
  background-color: #4c1d95;
  color: white;
  border: none;
  border-radius: 8px;
  padding: 12px 28px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

button:hover {
  background-color: #6d28d9;
  transform: scale(1.05);
}

.footer {
  font-size: 14px;
  color: #555;
  border-top: 1px solid #ddd;
  padding-top: 15px;
  margin-top: 20px;
}
```

## OUTPUT
<img width="960" height="837" alt="image" src="https://github.com/user-attachments/assets/9eca54ae-2b4c-456d-aced-5344f7ef5ad0" />
<img width="940" height="790" alt="image" src="https://github.com/user-attachments/assets/3299ad1d-dacd-4c1e-b03f-47465dbda140" />


## RESULT
The program for creating Image Carousel using React is executed successfully.
