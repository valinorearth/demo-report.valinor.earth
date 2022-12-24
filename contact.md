---
layout: page
title: Contact
permalink: /contact/
---

Email `(hi@oinam.com)` is always the first and best communication medium, and we are happy to get yours. We love thoughtful emails and would definitely reply. Please, tell me know who you are and your message be clear, and if you have a specific ask, an offer, an actionable item, or, well perhaps just a “Hi”.

---

<form id="contact-form" action="https://formspree.io/f/xayzweyw" method="POST">
  <fieldset>
    <p id="contact-form-status" style="font-weight: bold;"></p>
    <p>
      <label for="name">Name</label><br>
      <input type="text" name="name" required>
    </p>
    <p>
      <label for="email">Email</label><br>
      <input type="email" name="email" required>
    </p>
    <p>
      <label for="subject">Subject</label><br>
      <input type="text" name="subject" required>
    </p>
    <p>
      <label for="message">Message</label><br>
      <textarea cols="50" rows="10" name="message" required></textarea>
    </p>
    <button type="submit">Send Email</button>
  </fieldset>
</form>

<script>
var form = document.getElementById("contact-form");

async function handleSubmit(event) {
  event.preventDefault();
  var status = document.getElementById("contact-form-status");
  var data = new FormData(event.target);
  fetch(event.target.action, {
    method: form.method,
    body: data,
    headers: {
      'Accept': 'application/json'
    }
  }).then(response => {
    status.innerHTML = "Thanks! Email Sent.";
    form.reset()
  }).catch(error => {
    status.innerHTML = "Oops! Didn't work. Can you please retry?"
  });
}
form.addEventListener("submit", handleSubmit)
</script>


{% comment %}
## Archived

- [Blogspot](http://brajeshwar.blogspot.com)
- [Facebook](https://www.facebook.com/brajeshwar/)
- [Flickr](https://www.flickr.com/photos/brajeshwar/) `(2004-2015; 11+ million views)`
- [Reddit](https://www.reddit.com/user/Brajeshwar/)
- [WordPress](https://profiles.wordpress.org/brajeshwar/)
- Find more at https://discoverprofile.com/brajeshwar/
{% endcomment %}