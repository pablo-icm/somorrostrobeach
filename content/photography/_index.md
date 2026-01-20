---
title: "Photography"
description: "Black and white analog photography"
---

## Featured

{{< rawhtml >}}
<div style="margin-bottom: 3rem;">
    <div class="slideshow-container">
        <button class="slide-arrow prev" onclick="changeSlide(-1)">‹</button>

        <div class="slideshow" id="slideshow">
            <div class="slide">
                <img src="/images/planktographica/IMG_0244.jpg" alt="Planktographica 1">
                <div class="slide-caption">
                    <h3>Planktographica</h3>
                    <p>Exploring the hidden beauty of microscopic marine life through analog photography</p>
                </div>
            </div>

            <div class="slide">
                <img src="/images/photo/fageda-02.JPG" alt="Darkroom">
                <div class="slide-caption">
                    <h3>Darkroom works</h3>
                </div>
            </div>

            <div class="slide">
                <img src="/images/planktographica/IMG_0245.jpg" alt="Planktographica 2">
                <div class="slide-caption">
                    <h3>Planktographica</h3>
                    <p>Black and white silver gelatin prints from the darkroom</p>
                </div>
            </div>

            <div class="slide">
                <img src="/images/photo/sils-01.png" alt="Darkroom">
                <div class="slide-caption">
                    <h3>Darkroom works</h3>
                </div>
            </div>

            <div class="slide">
                <img src="/images/planktographica/IMG_0246.jpg" alt="Planktographica 3">
                <div class="slide-caption">
                    <h3>Planktographica</h3>
                    <p>Where science and art converge in the depths of the ocean</p>
                </div>
            </div>

            <div class="slide">
                <img src="/images/photo/part-alta-01.jpg" alt="Darkroom">
                <div class="slide-caption">
                    <h3>Darkroom works</h3>
                </div>
            </div>

            <div class="slide">
                <img src="/images/planktographica/IMG_0249.jpg" alt="Planktographica 4">
                <div class="slide-caption">
                    <h3>Planktographica</h3>
                    <p>Showing the ethereal forms of plankton</p>
                </div>
            </div>

            <div class="slide">
                <img src="/images/photo/fageda-01.jpg" alt="Darkroom">
                <div class="slide-caption">
                    <h3>Darkroom works</h3>
                </div>
            </div>


            <div class="slide">
                <img src="/images/planktographica/IMG_8630.jpg" alt="Planktographica 5">
                <div class="slide-caption">
                    <h3>Planktographica</h3>
                    <p>Traditional darkroom techniques meet scientific imagery</p>
                </div>
            </div>
        </div>

        <button class="slide-arrow next" onclick="changeSlide(1)">›</button>

        <div class="slideshow-controls">
            <button class="slide-dot active" onclick="goToSlide(0)"></button>
            <button class="slide-dot" onclick="goToSlide(1)"></button>
            <button class="slide-dot" onclick="goToSlide(2)"></button>
            <button class="slide-dot" onclick="goToSlide(3)"></button>
            <button class="slide-dot" onclick="goToSlide(4)"></button>
        </div>
    </div>
</div>

<script>
let currentSlide = 0;
const totalSlides = 8;
let autoSlideInterval;

function updateSlideshow() {
    const slideshow = document.getElementById('slideshow');
    const dots = document.querySelectorAll('.slide-dot');

    slideshow.style.transform = `translateX(-${currentSlide * 100}%)`;

    dots.forEach((dot, index) => {
        dot.classList.toggle('active', index === currentSlide);
    });
}

function changeSlide(direction) {
    currentSlide = (currentSlide + direction + totalSlides) % totalSlides;
    updateSlideshow();
    resetAutoSlide();
}

function goToSlide(index) {
    currentSlide = index;
    updateSlideshow();
    resetAutoSlide();
}

function resetAutoSlide() {
    clearInterval(autoSlideInterval);
    autoSlideInterval = setInterval(() => changeSlide(1), 5000);
}

document.addEventListener('DOMContentLoaded', function() {
    autoSlideInterval = setInterval(() => changeSlide(1), 5000);
});

document.addEventListener('keydown', function(e) {
    if (e.key === 'ArrowLeft') changeSlide(-1);
    if (e.key === 'ArrowRight') changeSlide(1);
});
</script>
{{< /rawhtml >}}

---

## Projects

{{< rawhtml >}}
<div class="cards-grid">

    <a href="/photography/darkroom-work/" class="project-card">
        <img src="/images/photo/fageda-02.JPG" alt="Darkroom Work" class="card-image">
        <div class="card-content">
            <h3 class="card-title">Darkroom Work</h3>
            <p class="card-description">
                Traditional silver gelatin printing in the darkroom. Each print is handcrafted using time-honored photographic techniques.
            </p>
            <div class="card-tags">
                <span class="card-tag">Silver Gelatin prints</span>
                <span class="card-tag">Darkroom printing</span>
                <span class="card-tag">Analog photography</span>
            </div>
        </div>
    </a>

</div>
{{< /rawhtml >}}

---

## Instagram (hardly updated)

{{< rawhtml >}}
<a href="https://instagram.com/el_pableras" target="_blank" class="contact-card" style="max-width: 400px; margin: 0 auto;">
    <div class="contact-icon instagram">📸</div>
    <div class="contact-info">
        <h3>Instagram</h3>
        <p>@el_pableras</p>
    </div>
</a>
{{< /rawhtml >}}
