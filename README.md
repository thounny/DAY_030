# DAY_030 | GSAP-Driven Animated Gallery

## Project Overview

For **DAY_030**, the final day of my 30-day daily code challenge, I created an **animated gallery** using **HTML**, **CSS**, **JavaScript**, and **GSAP**. This project showcases a minimalist design with dynamic image animations, scattered layout transitions, and a soft color palette. The gallery is inspired by my love for the anime *Serial Experiments Lain*, blending subtle chaos with calm minimalism to reflect the enigmatic atmosphere of the show.

---

## Preview

![DAY_030_1](./assets/DAY_030.gif)

## Inspiration

I was inspired by award-winning website designs from Awwwards and my love for *Serial Experiments Lain*. This anime's surreal and contemplative nature influenced my choice to create an experience where images scatter and subtly shift positions, adding an interactive layer that’s both playful and mysterious. Also we all love **lain**.

---

## Key Features

- **Minimalist Layout**: Soft background and unobtrusive navigation links for a clean aesthetic.
- **Dynamic Image Animations**: GSAP-powered animations that scatter and shrink images to specific positions, emulating the fragmented, introspective style of *Serial Experiments Lain*.
- **Smooth Transitions**: Animated text and images for a visually cohesive experience.
- **Brutalist Design Elements**: Bold yet minimal styling, emphasizing simplicity and functionality.

---

## JavaScript and Animation Details

### JavaScript Libraries Used

1. **GSAP (GreenSock Animation Platform)**:
   - Manages the initial load animations, text transitions, and image scattering effects.

### Animation Implementation

The JavaScript code uses **GSAP** to handle loading animations and position effects for the gallery images. The smooth transitions deliver an immersive experience, aligning with the layered and fragmented themes inspired by *Serial Experiments Lain*.

#### Step-by-Step Code Explanation

1. **Setting Up Initial Positions**:
   The images are first positioned in the center of the screen, with `scale(0)` to create an initial shrink effect.

   ```javascript
   gsap.set(".img", {
     top: "45%",
     left: "50%",
     transform: "translate(-50%, -50%) scale(0)",
   });
   ```

2. **Loading Animation for Text**:
   Each line of text in the header animates upwards into view, creating a subtle reveal effect.

   ```javascript
   gsap.from("p", {
     y: 40,
     ease: "power4.inOut",
     duration: 1,
     stagger: {
       amount: 0.15,
     },
     delay: 0.5,
   });
   ```

3. **Expanding and Scattering the Images**:
   After the initial text animation, each image in the gallery scales up to full size before scattering into specific positions across the screen.

   ```javascript
   gsap.to(".img", {
     scale: 1,
     width: "300px",
     height: "400px",
     stagger: 0.15,
     duration: 0.75,
     ease: "power2.out",
     delay: 1,
     onComplete: scatterAndShrink,
   });

   function scatterAndShrink() {
     gsap.to(".img", {
       top: (i) => positions[i].top,
       left: (i) => positions[i].left,
       transform: "none",
       width: "75px",
       height: "100px",
       stagger: 0.075,
       duration: 0.75,
       ease: "power2.out",
     });
   }
   ```

4. **Fade-Out of Header Text**:
   After the images settle, the header text fades out smoothly, adding to the clean, minimalistic experience.

   ```javascript
   gsap.to("p", {
     top: "40px",
     ease: "power4.inOut",
     duration: 1,
     stagger: {
       amount: 0.15,
     },
     delay: 3,
     onComplete: () => {
       document.querySelector(".header").remove();
     },
   });
   ```

5. **Fade-In for Navigation Links**:
   Finally, navigation links fade into view, providing smooth and unobtrusive access to external profiles.

   ```javascript
   gsap.from("a", {
     y: 20,
     opacity: 0,
     ease: "power2.out",
     duration: 1,
     stagger: {
       amount: 0.15,
     },
     delay: 4,
   });
   ```

### Layout Structure

The layout emphasizes a central text header and a scattered image gallery. Absolute positioning of images and the `gsap` animations achieve a visually balanced, interactive design.

---

## How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/thounny/DAY_030.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd DAY_030
   ```

3. **Open the `index.html` file** in your browser, or use a local development server like **Live Server** in VSCode.

---

## Project Structure

```bash
DAY_030/
│
├── assets/
├── fonts/
│   └── helveticaneue.woff2
├── images/
├── index.html
└── styles.css
```

---

## Technologies Used

- **HTML5**: Provides the foundational structure for the gallery layout.
- **CSS3**: Manages styling, absolute positioning, and aesthetic elements.
- **JavaScript (ES6)**: Controls animations and interaction.
- **GSAP (GreenSock Animation Platform)**: Powers the gallery animations and transitions.

---

## Author

![Logo](./assets/index_dwn.gif)

**Thounny Keo**  
Creative Developer & Designer  
Frontend Development Student | Year Up United

---

![Miku](./assets/miku.gif)