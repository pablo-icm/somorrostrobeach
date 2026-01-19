---
title: "Darkroom Work"
description: "Traditional silver gelatin printing"
cover:
    image: "/images/planktographica/IMG_0251.jpg"
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

## Process

### Film Development

1. Loading film in complete darkness
2. Careful temperature control during development
3. Stop bath, fixing, and washing
4. Drying and archiving negatives

### Printing

1. Contact sheets to select images
2. Test strips for exposure
3. Dodging and burning for local contrast control
4. Multiple test prints before the final version
5. Archival washing and toning

## Materials

- **Film**: Ilford HP5+, Kodak Tri-X, Fomapan
- **Paper**: Ilford Multigrade, Fomabrom
- **Chemistry**: Rodinal, ID-11, Multigrade developer
- **Toners**: Selenium, sepia

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
    <img src="/images/planktographica/IMG_0251.jpg" alt="Darkroom 1" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_8630.jpg" alt="Darkroom 2" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_8631.jpg" alt="Darkroom 3" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0244.jpg" alt="Darkroom 4" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_0245.jpg" alt="Darkroom 5" onclick="openLightbox(this.src)">
    <img src="/images/planktographica/IMG_8632.jpg" alt="Darkroom 6" onclick="openLightbox(this.src)">
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
