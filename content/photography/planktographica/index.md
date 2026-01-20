---
title: "Planktographica"
description: "Microscopic marine life through analog photography"
cover:
    image: "/images/planktographica/fanyella.png"
    alt: "Planktographica"
---

## About the Project

Planktographica is an artistic exploration of plankton through analog photography. Using traditional black and white techniques, I reveal the hidden beauty of microscopic marine life that usually escapes our perception.

## Concept

The world beneath the waves is filled with organisms of extraordinary beauty, yet invisible to the naked eye. These creatures—diatoms, dinoflagellates, copepods, and countless others—form the foundation of marine ecosystems and drive the planet's biogeochemical cycles.

Through Planktographica, I aim to:

- **Reveal hidden beauty**: Making the microscopic visible and tangible
- **Bridge science and art**: Using scientific imagery as artistic material
- **Preserve traditional techniques**: Employing analog photography in a digital age
- **Create emotional connections**: Fostering appreciation for marine microorganisms

## Technical Approach

### Photography

- **Film**: Black and white silver gelatin film
- **Format**: Medium and large format cameras
- **Processing**: Traditional darkroom development
- **Printing**: Hand-made silver gelatin prints

### Subject Matter

- Plankton samples collected from Mediterranean waters
- Microscopy preparations of marine microorganisms
- Abstract interpretations of microscopic structures

## Gallery

{{< rawhtml >}}
<style>
.photo-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
    margin: 2rem 0;
}
.photo-gallery img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 12px;
    cursor: pointer;
    transition: all 0.4s ease;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
}
.photo-gallery img:hover {
    transform: scale(1.02);
    box-shadow: 0 8px 30px rgba(0,0,0,0.3);
}
</style>

<div class="photo-gallery">
    <img src="/images/planktographica/IMG_0244.jpg" alt="Planktographica 1" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0245.jpg" alt="Planktographica 2" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0246.jpg" alt="Planktographica 3" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0249.jpg" alt="Planktographica 4" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0250.jpg" alt="Planktographica 5" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0251.jpg" alt="Planktographica 6" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_8630.jpg" alt="Planktographica 7" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_8631.jpg" alt="Planktographica 8" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_8632.jpg" alt="Planktographica 9" onclick="openLightbox(this.src)">
</div>

<div class="lightbox" id="lightbox" onclick="closeLightbox()">
    <span class="lightbox-close">&times;</span>
    <img id="lightbox-img" src="" alt="Full size image">
</div>

<script>
function openLightbox(src) {
    document.getElementById('lightbox-img').src = src;
    document.getElementById('lightbox').classList.add('active');
    document.body.style.overflow = 'hidden';
}
function closeLightbox() {
    document.getElementById('lightbox').classList.remove('active');
    document.body.style.overflow = '';
}
document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape') closeLightbox();
});
</script>
{{< /rawhtml >}}

## Exhibitions

*Information about exhibitions coming soon*

---

{{< rawhtml >}}
<a href="/photography/" class="contact-btn" style="margin-top: 2rem;">← Back to Photography</a>
{{< /rawhtml >}}
