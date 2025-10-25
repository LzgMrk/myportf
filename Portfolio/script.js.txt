// === Smooth Scroll Reveal ===
const sections = document.querySelectorAll("section");

const revealOnScroll = () => {
  const triggerBottom = window.innerHeight * 0.85;

  sections.forEach(section => {
    const boxTop = section.getBoundingClientRect().top;
    if (boxTop < triggerBottom) {
      section.classList.add("visible");
    }
  });
};

window.addEventListener("scroll", revealOnScroll);
window.addEventListener("load", revealOnScroll);

// === Slideshow (Smooth Fade Transition) ===
const slides = document.querySelectorAll(".slideshow img");
let current = 0;

function showNextSlide() {
  slides[current].classList.remove("active");
  current = (current + 1) % slides.length;
  slides[current].classList.add("active");
}

// Initial state
if (slides.length > 0) {
  slides[0].classList.add("active");
  setInterval(showNextSlide, 5000); // change every 5 seconds
}
