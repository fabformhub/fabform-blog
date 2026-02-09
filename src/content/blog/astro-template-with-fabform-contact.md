---
title: "Astro Template With Fabform Contact Form"
description: "A ready‑to‑use Astro template that includes a fully functional contact form powered by Fabform, with no serverless functions required."
pubDate: 2026-02-08
heroImage: '../../assets/blog-placeholder-3.jpg'
---

Astro is one of the best frameworks for building fast, content‑focused websites. Many developers want a simple way to add a contact form without setting up serverless functions or backend code. This template gives you a clean starting point: an Astro project with a fully integrated Fabform contact form that works on any static host.

If you are exploring other Astro or static‑site form setups, these guides may also help:

- [Astro Contact Form Without Serverless Functions](/blog/astro-contact-form-without-serverless)
- [Build an Astro Blog With a Fabform Contact Form](/blog/build-astro-blog-with-fabform-contact-form)
- [The Fastest Way to Add Forms to Static Sites](/blog/the-fastest-way-to-add-forms-to-static-sites)

---

## Why this template uses Fabform

Astro outputs static HTML by default. This means:

- no backend  
- no server‑side processing  
- no built‑in email sending  
- no form submission handling  

Fabform provides a backendless form endpoint that works with any static site. It includes:

- spam protection  
- email, Slack, and webhook notifications  
- a searchable dashboard  
- CSV export  
- GDPR‑friendly storage  

Your Astro site stays static.  
Your form becomes fully functional.

---

## Project structure

A typical Astro project using this template includes:

```
src/
  pages/
    index.astro
    contact.astro
  components/
    Layout.astro
public/
astro.config.mjs
package.json
```

The contact form lives in `src/pages/contact.astro`.

---

## Step 1 — Create your Fabform endpoint

1. Visit https://fabform.io  
2. Create a free account  
3. Select “Create New Form”  
4. Copy your unique form endpoint:

```
https://fabform.io/f/your-form-id
```

If you want to compare Fabform with other services, see:  
[Fabform vs Formspree](/blog/fabform-vs-formspree)

---

## Step 2 — Add the contact form to your Astro template

Create or edit `src/pages/contact.astro`:

```astro
---
title: "Contact"
---

<h1>Contact</h1>

<form action="https://fabform.io/f/your-form-id" method="POST">
  <label>
    Name
    <input type="text" name="name" required />
  </label>

  <label>
    Email
    <input type="email" name="email" required />
  </label>

  <label>
    Message
    <textarea name="message" required></textarea>
  </label>

  <button type="submit">Send Message</button>
</form>
```

This form works immediately.  
No JavaScript.  
No serverless functions.  
No backend code.

---

## Step 3 — Style your form

Add a `<style>` block to the same file or use a global stylesheet:

```astro
<style>
  form {
    max-width: 500px;
    margin: 2rem 0;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  input, textarea {
    padding: 0.75rem;
    border: 1px solid #ccc;
    border-radius: 6px;
  }

  button {
    padding: 0.75rem;
    background: #000;
    color: #fff;
    border: none;
    border-radius: 6px;
    cursor: pointer;
  }
</style>
```

---

## Step 4 — Test your form

Start your local server:

```
npm run dev
```

Visit:

```
http://localhost:4321/contact
```

Submit a test message.  
You will see it appear instantly in your Fabform dashboard.

---

## Step 5 — Deploy your Astro template

This template works on any static host, including:

- Netlify  
- Vercel  
- Cloudflare Pages  
- GitHub Pages  
- S3 + CloudFront  

If you are deploying to one of these platforms, you may find these guides helpful:

- [Netlify Contact Form Tutorial](/blog/netlify-contact-form-tutorial)  
- [Cloudflare Pages Contact Form Tutorial](/blog/cloudflare-pages-contact-form-tutorial)  
- [Add a Serverless Contact Form to GitHub Pages](/blog/add-serverless-contact-form-github-pages)

---

## Step 6 — Add spam protection

Fabform includes built‑in spam filtering, but you can add an optional honeypot field:

```html
<input type="text" name="website" style="display:none" tabindex="-1" autocomplete="off" />
```

Bots fill this field.  
Humans do not.  
Fabform ignores submissions that include it.

---

## Troubleshooting

### Form not submitting  
Verify your `action` attribute:

```
https://fabform.io/f/your-form-id
```

### Not receiving notifications  
Check your Fabform notification settings.

### Using a component‑based layout  
Ensure the form is not being rendered client‑side.

---

## Related Posts

- [Astro Contact Form Without Serverless Functions](/blog/astro-contact-form-without-serverless)  
- [Build an Astro Blog With a Fabform Contact Form](/blog/build-astro-blog-with-fabform-contact-form)  
- [Netlify Forms Alternative for Static Sites](/blog/netlify-forms-alternative-static-sites)  
- [Netlify Forms Not Working? Fix It Fast](/blog/netlify-forms-not-working-fix)

---

## Final Thoughts

This Astro template gives you a clean starting point for any content‑driven site, with a fully functional contact form already integrated. If you want a consistent form workflow across Astro, Netlify, Cloudflare Pages, and GitHub Pages, Fabform provides a unified backend that works everywhere without serverless complexity.

