---
layout: post
title:  "Explore Pokémon Like Never Before!"
summary: "A fun and interactive way to browse and search Pokémon with infinite scroll, hosted on Vercel"
author: mariecheo
date: '2024-06-03 19:00:00 +0000'
category: projects
thumbnail: /assets/img/posts/pokemon.jpeg
keywords: pokemon app, react, infinite scroll, vercel, github, search pokemon, pokedex
permalink: /blog/explore-pokemon-app/
usemathjax: false
---

Ever wished for a Pokédex that’s fast, simple, and fun to use? This Pokémon web app lets you scroll through hundreds of Pokémon effortlessly — with images, names, and all the essential info displayed in a clean, modern layout.

### ✨ Features

- **🔍 Smart Search**: Type the name of a Pokémon and after a short pause, results that match your input will appear. No need to press enter.
- **♾️ Infinite Scrolling**: Browse all available Pokémon without clicking next — more appear automatically as you scroll.
- **🧼 Easy Reset**: A reset button clears your search and brings you back to the full list instantly.

### 🚀 Hosted on Vercel

The app is deployed on [Vercel](https://vercel.com), which offers fast, reliable, and free hosting optimized for frontend frameworks like React. Every time you push updates to your GitHub repository, Vercel automatically builds and deploys the latest version of the app, ensuring continuous deployment with minimal effort.

Try it live here: [My Pokemon App](https://myp-pokemon-ap.vercel.app)

### 🛠️ Get Started Locally

Want to run the project on your own computer or contribute?

1. **Clone the Repository and Install Dependencies**
   ```bash
   git clone https://github.com/NoellaMarie501/Myp-Pokemon-AP.git
   cd pokemon-app


```bash
npm install
```

2. **Run the Development Server**

```bash
npm start
```

Open your browser and navigate to [http://localhost:3000](http://localhost:3000).

---

## ⚙️ Technical Details to practice your skills using this app

- **Built with React**  
  Utilizes functional components and React hooks (`useState`, `useEffect`) for state management and lifecycle control.

- **API Data Fetching**  
  Fetches Pokémon data from the public [PokéAPI](https://pokeapi.co) using `fetch` and Axios for reliable HTTP requests.

- **Infinite Scroll Implementation**  
  Uses an intersection observer to detect when the user nears the bottom of the list and automatically loads more Pokémon in batches, improving performance by lazy loading data.

- **Debounced Search Input**  
  Implements a debounce function to reduce API calls while typing, sending search queries only after the user pauses typing for 300ms.

- **State Management**  
  Manages search input, loading states, and Pokémon data efficiently with React hooks.

- **Responsive Design**  
  Styled with CSS Flexbox and Grid for a layout that adapts smoothly across devices.

- **Deployment on Vercel**  
  Connected to GitHub via Vercel. Every push to the main branch triggers an automatic build and deployment, ensuring your app is always live with the latest updates.

- **Environment Optimization**  
  Vercel’s CDN and serverless infrastructure provide low-latency content delivery worldwide.

- **Code Quality**  
  Includes ESLint and Prettier configurations for consistent code style and easier collaboration.

---

## Contributing

Feel free to explore the code, submit issues, or contribute new features via pull requests. Happy coding! 🎉