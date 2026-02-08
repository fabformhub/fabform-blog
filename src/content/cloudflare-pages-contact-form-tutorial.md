---
title: "How to Set Up a Cloudflare Pages Site with a Backendless Contact Form"
description: "Step-by-step beginner guide to creating a Cloudflare Pages website and adding a backendless contact form using Fabform."
pubDate: 2026-02-08
heroImage: '../../assets/blog-placeholder-3.jpg'
---

# How to Set Up a Cloudflare Pages Site with a Backendless Contact Form

Cloudflare Pages makes it easy to host static websites with fast, global performance. In this guide, we’ll show you **how to create a Cloudflare Pages site and add a fully functional, backendless contact form using Fabform** — no servers required.

---

## 1. Create a Cloudflare Account

1. Go to [https://dash.cloudflare.com/sign-up](https://dash.cloudflare.com/sign-up)  
2. Create an account with your email and password  
3. Verify your email address  

---

## 2. Create a New Cloudflare Pages Project

1. Log in to Cloudflare  
2. Go to **Pages → Create a project**  
3. Connect your GitHub account to Cloudflare Pages  
4. Select a repository for your site (you can create a new one or use an existing repo)  
5. Click **Begin Setup**  

---

## 3. Configure the Project

1. For a simple static site:
   - Framework preset: **None (Static Site)**  
   - Root directory: `/`  
   - Build command: leave blank  
   - Output directory: leave blank  

2. Click **Save and Deploy**  

> Cloudflare Pages will automatically build and deploy your site. You’ll get a URL like:  
> `https://your-site.pages.dev`

---

## 4. Add Your HTML Files

1. In your repository, create an `index.html` file  
2. Add your website HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Cloudflare Pages Site</title>
</head>
<body>
  <h1>Welcome to My Site</h1>
  <p>Contact me using the form below:</p>

  <form action="https://fabform.com/YOUR_PROJECT_KEY" method="POST">
    <input type="text" name="name" placeholder="Your Name" required>
    <input type="email" name="email" placeholder="Your Email" required>
    <textarea name="message" placeholder="Your Message" required></textarea>
    <button type="submit">Send</button>
  </form>
</body>
</html>

