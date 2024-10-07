Here’s how you can include all the media queries within your CSS file, ensuring responsiveness for various screen sizes. I've improved your code by refining the breakpoints and applying the `clamp()` function for fluid typography.

### Full CSS with Media Queries:

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --bg-color: #e5e5fd;
    --dark-black: #1d1e4c;
}

html {
    font-size: 62.5%; /* 1rem = 10px */
}

body {
    font-family: "Inter", system-ui;
    background-color: var(--bg-color);
}

.container {
    background: var(--bg-color);
    min-height: 100vh;
    border: 1rem solid var(--dark-black);
}

.content {
    max-width: 1280px;
    width: 90%;
    margin: 0 auto;
}

.top_section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 10rem;
    gap: 2rem;
}

.image_container {
    border-radius: 30%;
    width: 300px;
    height: 320px;
    overflow: hidden;
}

.image_container img {
    max-width: 100%;
    height: auto;
}

.text_container h1 {
    font-size: clamp(2.4rem, 5vw, 5rem);
    font-weight: bold;
    color: var(--dark-black);
    text-transform: uppercase;
}

.text_container h4 {
    font-size: clamp(1.6rem, 3vw, 3rem);
    text-align: end;
}

.about_section {
    margin-top: 5rem;
}

.about_section h2 {
    font-size: clamp(2rem, 6vw, 7.2rem);
    font-weight: 500;
    margin-bottom: 2rem;
}

.about_section p {
    font-size: clamp(1.6rem, 2.5vw, 2rem);
    line-height: 1.8;
    letter-spacing: 1px;
    text-align: justify;
}

.biography_section {
    margin: 5rem 0;
}

.biography_section h3 {
    font-size: clamp(1.8rem, 2.5vw, 2.4rem);
    margin-bottom: 2rem;
}

.biography_section ul {
    margin-left: 2rem;
}

.biography_section ul li {
    font-size: clamp(1.2rem, 1.5vw, 1.4rem);
    margin-bottom: 1.5rem;
}

.footer {
    margin: 5rem 0;
}

.footer p {
    text-align: center;
    font-size: clamp(1rem, 1.5vw, 1.2rem);
}

/* Media Queries */

/* Tablet: Screens smaller than 1024px */
@media screen and (max-width: 1024px) {
    .content {
        padding: 1rem;
    }

    .top_section {
        flex-direction: column;
        align-items: center;
        gap: 4rem;
    }

    .text_container h1 {
        text-align: center;
    }

    .about_section h2 {
        font-size: clamp(2rem, 5vw, 5.2rem);
    }

    .about_section {
        margin-top: 7rem;
    }

    .about_section p {
        font-size: 1.8rem;
    }
}

/* Mobile: Screens smaller than 768px */
@media screen and (max-width: 768px) {
    .top_section {
        gap: 3rem;
    }

    .text_container h1 {
        font-size: 3rem;
        font-weight: 400;
        text-align: center;
    }

    .text_container h4 {
        font-size: 2.4rem;
        font-weight: 400;
        text-align: center;
    }

    .about_section {
        margin-top: 4rem;
    }

    .about_section h2 {
        font-size: 3rem;
        margin-bottom: 1rem;
    }

    .about_section p {
        font-size: 1.6rem;
        text-align: justify;
    }

    .biography_section h3 {
        font-size: 2rem;
    }

    .footer p {
        font-size: 1.2rem;
        text-align: center;
    }
}

/* Small Mobile: Screens smaller than 480px */
@media screen and (max-width: 480px) {
    .text_container h1 {
        font-size: 2.4rem;
    }

    .text_container h4 {
        font-size: 2rem;
    }

    .about_section h2 {
        font-size: 2.5rem;
        margin-bottom: 0.5rem;
    }

    .about_section p {
        font-size: 1.4rem;
        line-height: 2rem;
    }

    .footer p {
        font-size: 1rem;
        text-align: center;
    }
}
```

### Key Changes:
1. **`clamp()` function**: This automatically adjusts the font size depending on the viewport size.
2. **Media Queries**: 
   - For `max-width: 1024px`, the layout becomes more compact for tablets.
   - For `max-width: 768px`, the font sizes, gaps, and layout are reduced for smaller tablets and larger mobile devices.
   - For `max-width: 480px`, the layout is more compact, with even smaller text and margins for mobile devices.

This should ensure a more fluid, responsive design across different screen sizes. Let me know if you'd like further adjustments!