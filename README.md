<form action="https://<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>
  <h2>Contact Us</h2>
<form   action="https://formspree.io/f/xrbqbryo}"   class="fs-form"   target="_top"   method="POST" >   <div class="fs-field">     <label class="fs-label" for="name">Name</label>     <input class="fs-input" id="name" name="name" required />   </div>   <div class="fs-field">     <label class="fs-label" for="email">Email Address</label>     <input class="fs-input" id="email" name="email" required />   </div>   <div class="fs-field">     <label class="fs-label" for="number">Phone Number</label>     <input class="fs-input" id="number" name="number" required />   </div>   <div class="fs-field">
    <label class="fs-label" for="message">WHAT SERVICES ARE YOU LOOKING FOR?</label>
    <p class="fs-description">We usually respond within 1-2 business days.</p>
  </div>
  <div class="fs-button-group">
    <button class="fs-button" type="submit">Send</button>
  </div>
</form>
<script>
  const form = document.getElementById('contact-form');
  const status = document.getElementById('form-status');

  form.addEventListener('submit', async (e) => {
    e.preventDefault();
    const data = new FormData(form);
    try {
      const res = await fetch("https://formspree.io/f/xrbqbryo", {
        method: "POST",
        body: data,
        headers: { 'Accept': 'application/json' }
      });
      if (res.ok) {
        status.textContent = "Thank you! Your message has been sent.";
        form.reset();
      } else {
        status.textContent = "Oops! There was a problem.";
      }
    } catch (err) {
      status.textContent = "Error submitting form.";
    }
  });
</script>
