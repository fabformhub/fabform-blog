---
title: "How to Set Up a Netlify Site with a Backendless Contact Form"
description: "Step-by-step guide for beginners to create a Netlify website and add a backendless contact form using Fabform."
pubDate: 2026-02-08
heroImage: '../../assets/blog-placeholder-3.jpg'
---

# How to Set Up a Netlify Site with a Backendless Contact Form

Netlify makes it easy to host static websites with automatic deployment and free SSL. In this tutorial, we’ll show you **how to create a Netlify site and add a fully functional contact form using Fabform**, no backend required.

---

## 1. Create a Netlify Account

1. Go to [https://app.netlify.com/signup](https://app.netlify.com/signup)  
2. Sign up using GitHub, GitLab, or email  
3. Verify your email address  

---

## 2. Create a New Site

1. Log in to Netlify  
2. Click **New Site from Git**  
3. Connect your GitHub, GitLab, or Bitbucket account  
4. Select the repository you want to deploy (you can create a new one for this tutorial)  
5. Keep **build settings** as default for a simple static site:  
   - Build command: leave empty  
   - Publish directory: `/`  
6. Click **Deploy site**  

> Netlify will build and deploy your site. You’ll get a URL like:  
> `https://your-site.netlify.app`

---

## 3. Add Your HTML Files

1. In your repository, create an `index.html` file  
2. Add the website and contact form HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Netlify Site</title>
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

