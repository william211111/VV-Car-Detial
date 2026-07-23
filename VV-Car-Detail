// VV Detailing — basisfunktioner

document.addEventListener("DOMContentLoaded", () => {

  // Årstal i footer
  const yearEl = document.getElementById("year");
  if (yearEl) yearEl.textContent = new Date().getFullYear();

  // Mobilmenu
  const toggle = document.querySelector(".nav-toggle");
  const nav = document.querySelector(".main-nav");
  if (toggle && nav) {
    toggle.addEventListener("click", () => {
      const isOpen = nav.classList.toggle("is-open");
      toggle.setAttribute("aria-expanded", isOpen ? "true" : "false");
    });
  }

  // Scroll-reveal for sektioner
  const revealTargets = document.querySelectorAll(
    ".service-card, .bundle-card, .process-steps li"
  );
  revealTargets.forEach((el) => el.classList.add("reveal"));

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("is-visible");
          observer.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.15 }
  );
  revealTargets.forEach((el) => observer.observe(el));

  // Booking-formular (midlertidig — uden backend)
  const form = document.getElementById("booking-form");
  const status = document.getElementById("form-status");

  if (form) {
    form.addEventListener("submit", (e) => {
      e.preventDefault();

      const name = form.name.value.trim();
      if (!name) {
        status.textContent = "Udfyld venligst dit navn.";
        return;
      }

      // TODO: erstat med rigtigt booking-endpoint (fx Formspree, Netlify Forms
      // eller eget API), når hjemmesiden er live.
      status.textContent = `Tak, ${name}! Vi vender tilbage inden for 24 timer.`;
      form.reset();
    });
  }
});
