---
title: "How to Build an Astro Site From a Template and Add a Working Fabform Contact Form"
description: "Learn how to create a new Astro site from a template and integrate a fully functional Fabform contact form into your pages. No serverless functions, no backend code—just clean, modern static-site development."
pubDate: 2025-03-01
heroImage: '../../assets/blog-placeholder-3.jpg'
---

Astro makes it incredibly easy to build fast, content‑focused websites using templates. But the moment you need a working contact form, most tutorials push you toward serverless functions or backend code. That’s unnecessary. You can add a fully functional contact form to any Astro template using Fabform in minutes.

This guide walks you through:

- Creating a new Astro site from a template  
- Adding a contact page  
- Integrating a Fabform endpoint  
- Adding spam protection  
- Deploying your site with a working form  

Everything is HTML‑first, zero‑backend, and works on any static host.

---

## 1. Create a New Astro Project From a Template

Astro has an official templates gallery, but the most popular starting point is the **Astro Blog Template**.

Create a new project:

```bash
npm create astro@latest my-astro-site
```

When prompted:

- Choose **Blog** template  
- Choose **TypeScript or JavaScript** (your preference)  
- Choose **No** for server-side rendering  
- Install dependencies  

Then move into your project:

```bash
cd my-astro-site
npm install
```

Start the dev server:

```bash
npm run dev
```

Your new Astro site is now running locally.

---

## 2. Create a Fabform Endpoint

Go to **https://fabform.io** and:

1. Create a new form  
2. Copy your unique endpoint URL, which looks like:

```
https://fabform.io/f/your-form-id
```

This URL is your entire backend. No serverless functions. No API routes. No configuration.

---

## 3. Add a Contact Page to Your Astro Site

Inside your project, create a new page:

```
src/pages/contact.astro
```

Add the following:

```astro
---
title: "Contact"
---

<h1>Contact Me</h1>
<p>Have a question or want to reach out? Send a message below.</p>

<form
  action="https://fabform.io/f/your-form-id"
  method="POST"
  class="space-y-4 max-w-md"
>
  <label>
    <span>Your Name</span>
    <input type="text" name="name" required />
  </label>

  <label>
    <span>Email</span>
    <input type="email" name="email" required />
  </label>

  <label>
    <span>Message</span>
    <textarea name="message" required></textarea>
  </label>

  <button type="submit">Send Message</button>
</form>
```

Your form now works instantly.

---

## 4. Add a Success Page (Optional but Recommended)

Create:

```
src/pages/success.astro
```

Add:

```astro
---
title: "Message Sent"
---

<h1>Thanks for your message!</h1>
<p>I’ll get back to you soon.</p>
```

Update your form to redirect after submission:

```html
<form
  action="https://fabform.io/f/your-form-id?redirect=/success"
  method="POST"
>
```

---

## 5. Add Spam Protection (No CAPTCHA Needed)

Fabform includes automatic spam filtering, but you can add a honeypot field:

```html
<input type="text" name="_honeypot" style="display:none" />
```

Bots fill it. Humans don’t. Spam disappears.

---

## 6. Deploy Your Astro Site

This setup works on:

- Cloudflare Pages  
- Netlify  
- Vercel  
- GitHub Pages  
- Any static host  

Build your site:

```bash
npm run build
```

Then deploy using your preferred platform.

Your contact form will work immediately—no serverless functions, no backend code, no configuration.

---

## Final Thoughts

Astro’s HTML‑first approach pairs perfectly with Fabform’s zero‑backend form handling. Instead of wrestling with serverless functions or debugging Netlify Forms, you get:

- A working contact form in minutes  
- File upload support  
- Strong spam protection  
- Clean HTML  
- Zero backend maintenance  
- A one‑time payment model instead of subscriptions  

If you’re building a static site with Astro, Fabform is the simplest and most reliable way to add a fully functional contact form.


