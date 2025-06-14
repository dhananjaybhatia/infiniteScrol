🌀 Infinite Scroll Anime App

This is a Next.js 14+ (App Router) web app that displays anime cards using infinite scroll. As the user scrolls down, new anime are dynamically fetched from the Shikimori API and displayed with smooth animations using Framer Motion.

🚀 Tech Stack
Next.js 14+ with App Directory

Framer Motion for animations

- react-intersection-observer for detecting scroll position

- Next.js Image for optimized image loading

- Server Actions for server-side fetching

📸 Features
✅ Server-side rendering of the first page of anime

✅ Infinite scroll using IntersectionObserver

✅ Smooth fade-in animation for each card

✅ Fully optimized image loading with next/image

🧠 How It Works
Here’s a high-level explanation of the flow:

1. Server-Side Rendering (page.tsx)
- The home page is a Server Component, which calls the fetchAnime(1) server action to fetch the first page of anime data.

- fetchAnime() calls the Shikimori API and returns an array of <AnimeCard /> components, each representing one anime.

- These cards are rendered immediately on page load.

2. Client-Side Infinite Scroll (LoadMore.tsx)
- LoadMore is a Client Component that uses the react-intersection-observer hook.

- It shows a spinner at the bottom of the page.

- When the spinner enters the viewport (i.e., the user scrolls to it), the app:

- Calls fetchAnime(page) again

- Appends the new <AnimeCard />s to local state

- Increments the page number

3. Animation with Framer Motion
- Each AnimeCard uses motion.div from Framer Motion.

- The animation delays each card's appearance slightly based on its index.

- This creates a staggered fade-in effect as cards load.

