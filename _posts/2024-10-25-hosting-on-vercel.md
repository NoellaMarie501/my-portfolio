---
layout: post
title: "How to Host Your React App on Vercel: A Step-by-Step Guide"
summary: "Learn how to deploy your React application easily and quickly with Vercel’s powerful hosting platform."
author: mariecheo
date: '2024-10-25 20:30:00 +0000'
category: tutorials
thumbnail: /assets/img/posts/vercel.png
keywords: vercel, react, hosting, deployment, github, continuous deployment, frontend hosting
permalink: /blog/how-to-host-react-on-vercel/
usemathjax: false
---

Hosting your React app has never been easier thanks to [Vercel](https://vercel.com). Whether you’re building a personal portfolio, a side project, or a production app, Vercel offers free, fast, and reliable hosting with automatic deployment from GitHub.

Here’s a step-by-step guide to get your React app live on Vercel in minutes.

---

### Why Choose Vercel?

- **Zero Configuration**: Vercel auto-detects React apps and builds them with zero setup.
- **Continuous Deployment**: Push your code to GitHub and your site updates automatically.
- **Global CDN**: Your app is served from edge servers worldwide, ensuring fast load times.
- **Custom Domains & HTTPS**: Easily add domains with free SSL certificates.
- **Free Tier**: Great for personal and small projects with generous limits.

---

### Step 1: Prepare Your React App

Make sure your React app is ready to be deployed. If you don’t have one yet, create a new app with:

```bash
npx create-react-app my-react-app
cd my-react-app


## Test it locally

Run your app locally to make sure everything works:

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser and verify the app runs fine.

---

## Step 2: Push Your Code to GitHub

Initialize Git if you haven’t already:

```bash
git init
git add .
git commit -m "Initial commit"
```

Create a new GitHub repository (e.g., `my-react-app`).

Link your local repo to GitHub and push your code:

```bash
git remote add origin https://github.com/yourusername/my-react-app.git
git push -u origin main
```

---

## Step 3: Connect Your Repository to Vercel

1. Go to [https://vercel.com](https://vercel.com) and sign up or log in (you can use GitHub to sign in).

2. Click **New Project**.

3. Select your GitHub repository (`my-react-app`).

4. Vercel will automatically detect your React app and pre-fill the build settings:

   - **Build Command:** `npm run build`  
   - **Output Directory:** `build`

5. Click **Deploy**.

---

## Step 4: Wait for Deployment

Vercel will start building your app. You can watch the build logs in real-time.

Once complete, your app will be live at a URL like:

```plaintext
https://my-react-app.vercel.app
```

You can share this link immediately!

---

## Step 5: Enable Continuous Deployment

Every time you push changes to your GitHub repository, Vercel automatically rebuilds and redeploys your app. This keeps your live site always up-to-date — no manual steps needed.

---

## Bonus: Add a Custom Domain (Optional)

1. In your Vercel dashboard, open your project settings.

2. Go to the **Domains** section and add your custom domain.

3. Follow the instructions to update your DNS records.

4. Vercel automatically provisions HTTPS certificates for secure connections.

---

## Summary

| Step              | Command / Action                              |
|-------------------|----------------------------------------------|
| Create React app: |  `npx create-react-app my-react-app`           |
| Push to GitHub:   |  `git push -u origin main`                      |
| Connect to Vercel | Select repo in Vercel dashboard                |
| Deploy            | Click Deploy, wait for build & deploy          |
| Update live site  | Push commits to GitHub; Vercel redeploys automatically |

---

## Conclusion

With Vercel, deploying your React app is quick and painless. No complex server setups or configurations — just connect your GitHub repo, deploy, and keep coding!

Happy deploying!