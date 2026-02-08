---
title: "How to Set Up a GitHub Pages Site with a Backendless Contact Form"
description: "A complete beginner's guide to creating a GitHub Pages website and adding a backendless contact form using Fabform."
pubDate: 2026-02-08
heroImage: '../../assets/blog-placeholder-3.jpg'
---

# How to Set Up a GitHub Pages Site with a Backendless Contact Form

If you want a simple website with a contact form but don’t want to manage a backend, GitHub Pages + Fabform is a perfect solution. This guide walks you through **every step**, from creating a GitHub account to deploying your site with a working contact form.

---

## 1. Create a GitHub Account

If you don’t already have a GitHub account:

1. Go to [https://github.com](https://github.com)  
2. Click **Sign Up**  
3. Follow the instructions to create your username, email, and password  
4. Verify your email address  

---

## 2. Create a New Repository for Your Website

1. Log in to GitHub  
2. Click the **+** icon in the top right and select **New repository**  
3. Name your repository (e.g., `my-website`)  
4. Make it **public**  
5. Check **Add a README file**  
6. Click **Create repository**  

---

## 3. Enable GitHub Pages

1. Go to your repository  
2. Click **Settings → Pages**  
3. Under **Source**, select `main` branch and `/ (root)` folder  
4. Click **Save**  
5. GitHub will generate a URL like:  

https://your-username.github.io/my-website/

---

## 4. Add Your Website Files

1. Go to your repository and click **Add file → Create new file**  
2. Name the file `index.html`  
3. Add basic HTML for your site:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>My GitHub Pages Site</title>
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

