---
title: "Build a Complete Astro Blog: From Template Setup to a Fully Functional Contact Form with Fabform"
description: "Learn how to create a fast, modern static blog using the official Astro Blog template and enhance it with a fully working contact form powered by Fabform. This step‑by‑step guide covers setup, customization, form integration, and deployment."
pubDate: 2025-01-01
heroImage: '../../assets/blog-placeholder-3.jpg'

---


# **Build a Complete Astro Blog: From Template Setup to a Fully Functional Contact Form with Fabform**

Astro has quickly become one of the most popular static site builders thanks to its speed, simplicity, and ability to ship zero JavaScript by default. In this tutorial, you’ll build a complete static blog using the official Astro Blog template — then enhance it with a fully functional contact form powered by **Fabform**, a backend‑free form handling service perfect for static sites.

You’ll walk away with:

- A fully working Astro blog  
- A clean project structure ready for customization  
- A production‑ready contact form with spam protection  
- A deployable static site that requires **no backend**  

---

# 1. Prerequisites

You’ll need:

- Node.js 18+  
- A terminal  
- Git (optional but recommended)  
- A Fabform account (free tier works perfectly)

---

# 2. Create a New Astro Project

Astro provides a CLI that scaffolds everything for you.

```bash
npm create astro@latest
```

Choose:

- **Template:** `Blog`  
- **TypeScript:** your preference  
- **Install dependencies:** Yes  
- **Add integrations:** Skip for now  

Your project structure will look like:

```
/
├─ public/
├─ src/
│  ├─ components/
│  ├─ content/
│  ├─ layouts/
│  ├─ pages/
│  └─ styles/
├─ astro.config.mjs
├─ package.json
└─ tsconfig.json
```

Run the dev server:

```bash
npm run dev
```

Visit `http://localhost:4321` — you now have a working Astro blog.

---

# 3. Customize the Blog Template (Optional but Recommended)

Astro’s blog template includes:

- Markdown‑powered posts  
- A homepage listing posts  
- A post layout  
- A global layout  
- A header and footer  

You can customize:

### Site title  
Edit `src/config.ts`:

```ts
export const SITE_TITLE = "My Astro Blog";
export const SITE_DESCRIPTION = "A fast, modern blog built with Astro.";
```

### Homepage content  
Edit `src/pages/index.astro`.

### Add new posts  
Create Markdown files in:

```
src/content/blog/my-post.md
```

---

# 4. Create a Contact Page

Add a new file:

```
src/pages/contact.astro
```

Paste this starter markup:

```astro
---
import Layout from "../layouts/Layout.astro";
---

<Layout title="Contact">
  <h1>Contact Me</h1>
  <p>Have a question or want to reach out? Fill out the form below.</p>

  <form
    method="POST"
    action="https://fabform.io/f/YOUR-FABFORM-ENDPOINT"
  >
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
</Layout>
```

Don’t worry about the endpoint yet — we’ll get it from Fabform.

---

# 5. Create a Fabform Endpoint

1. Log in to **fabform.io**  
2. Click **Create Form**  
3. Choose **Static Site Form**  
4. Name it something like `astro-blog-contact`  
5. Copy your unique endpoint URL, which looks like:

```
https://fabform.io/f/abc123
```

Replace the placeholder in your form:

```astro
action="https://fabform.io/f/abc123"
```

Fabform automatically handles:

- Form submissions  
- Email notifications  
- Spam filtering  
- Submission storage  
- Optional reCAPTCHA  

No backend required.

---

# 6. Add Basic Styling (Optional)

You can style the form using Astro’s global stylesheet:

`src/styles/global.css`:

```css
form {
  display: grid;
  gap: 1rem;
  max-width: 500px;
}

input,
textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ccc;
  border-radius: 6px;
}

button {
  background: #4f46e5;
  color: white;
  padding: 0.75rem 1rem;
  border-radius: 6px;
  border: none;
  cursor: pointer;
}
```

---

# 7. Test Your Contact Form

Run your dev server:

```bash
npm run dev
```

Go to:

```
http://localhost:4321/contact
```

Submit a test message.

Check your Fabform dashboard — you should see the submission instantly.

---

# 8. Build and Deploy Your Site

Astro outputs static HTML by default.

Build:

```bash
npm run build
```

Preview:

```bash
npm run preview
```

You can deploy to:

- Netlify  
- Vercel  
- Cloudflare Pages  
- GitHub Pages  
- Any static host  

All work perfectly with Fabform.


You now have:

- A complete Astro blog  
- A clean contact page  
- A working form powered by Fabform  
- A fully static site with zero backend maintenance  

This setup is fast, secure, and perfect for personal blogs, portfolios, or small business sites.

