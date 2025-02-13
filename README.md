Table of Contents

Overview

The Challenge

Screenshot

Links

Setup

My Process

Built With

Key Learnings

Challenges & Solutions

Accessibility Considerations

Future Improvements

Overview

The Challenge

Users should be able to:

View the optimal layout for the app across different screen sizes ✅

See hover states for all interactive elements ✅

Add/Remove products from the cart ✅

Edit product quantities in the cart ✅

Fill in all required fields during checkout ✅

Receive form validation feedback for missing or incorrect fields ✅

See accurate checkout totals based on cart contents ✅

Shipping adds a fixed $50 to the order ✅

VAT is calculated as 20% of the product subtotal (excluding shipping) ✅

Receive an order confirmation modal with a summary after checkout ✅

Bonus: Persist cart data across page refreshes using localStorage ✅

Screenshot



Links

Live Site URL

Setup

To run this project locally:

yarn && yarn dev

or

npm install && npm run dev

My Process

Built With

Next.js – For its server-side rendering & static site generation

Chakra UI – Component library with built-in accessibility features

Redux Toolkit – State management for cart and checkout flow

React-Hook-Form – Form validation and state management

Framer Motion – Smooth animations & transitions

React-Intersection-Observer – Lazy loading and animations on scroll

TypeScript – Ensuring type safety

Atomic Design System – Organized component structure

Mobile-First Workflow – Optimized for responsive design

Key Learnings

Chakra UI

I explored Chakra UI for the first time, having previously used Styled Components. I chose it over alternatives like Theme UI and Material UI due to its accessibility-first approach and recommendation in Next.js tutorials by Lee Robinson.

What I love about Chakra UI:

Built-in responsive styles using objects or arrays:

<Stack
  as="ul"
  spacing={{ base: '1rem', md: '2.125rem' }}
  direction={{ base: 'column', sm: 'row' }}
>

as prop allows swapping default HTML elements seamlessly

Custom hooks, like useDisclosure, simplify UI state management (e.g., opening/closing modals)

Next.js

Next.js simplifies file-based routing, static and server rendering, and API handling with minimal configuration. I leveraged getStaticProps for pre-fetching product data at build time from a JSON file.

Challenges & Solutions

Styling Active Navigation Links

Unlike React Router’s NavLink, Next.js Link doesn’t have built-in active state styling. My initial solution was to wrap Link with a custom component using useRouter:

const { asPath } = useRouter();

color={asPath === link.url ? 'accent' : 'white'}

For accessibility, I also wrapped Link in a custom component to add aria-current="page" dynamically.

Redux Toolkit for Cart State

Redux Toolkit streamlined state management, reducing boilerplate code. Instead of manually handling reducers and actions, I used slices. I also persisted the cart state to localStorage following Dan Abramov’s best practices.

store.subscribe(() => {
  localStorage.setItem('cart', JSON.stringify(store.getState().cart));
});

Accessibility Considerations

Used aria-disabled instead of disabled for inclusive button behavior (read more).

Implemented Skip to Content links to enhance keyboard navigation.

Future Improvements

Implement unit and integration tests using Jest & React Testing Library.

Optimize image loading with Next.js’s next/image for better performance.

Implement a backend API to replace the static JSON data for scalability.

Improve checkout flow with third-party payment integration.

This project was a valuable learning experience in building an optimized, accessible, and performant eCommerce site using modern frontend technologies. 🚀

