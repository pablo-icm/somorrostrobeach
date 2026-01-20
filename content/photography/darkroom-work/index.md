---
title: "Analog photography and Darkroom Work"
description: "Traditional silver gelatin printing"
cover:
    image: "/images/photo/olivera.jpg"
    alt: "Darkroom Work"
---

## The Darkroom

In an age of digital immediacy, the darkroom offers something different: slowness, intention, and the magic of watching an image emerge from nothing in a tray of developer.

## Why Analog?

Working with film and traditional printing processes offers unique qualities:

- **Tactile experience**: Physical negatives and prints you can hold
- **Tonal range**: The distinctive quality of silver gelatin
- **Intentionality**: Each print is a deliberate creation
- **Permanence**: Properly processed prints can last centuries
- **Meditative process**: The darkroom as a space for contemplation


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
    <img src="/images/photo/fageda-01.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/fageda-02.JPG" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/olivera.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/sils-01.png" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/sayago-1.png" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/pereIV.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/part-alta-01.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/part-alta-02.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/pisci-01.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/photo/gazte-01.png" alt="Darkroom 1" onclick="openLightbox(this.src)">
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

---

{{< rawhtml >}}
<a href="/photography/" class="contact-btn" style="margin-top: 2rem;">← Back to Photography</a>
{{< /rawhtml >}}
