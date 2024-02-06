# React Portfolio Site with Theme Switching

Build a responsive portfolio website using Next.js, React, and Tailwind CSS that supports dynamic theme switching (light and dark modes) and user preferences (e.g., font size, reduced motion). This project will utilize `useReducer` and `Context` for state management.

## Building Your Portfolio Site

- **Hero Section**: Introduce yourself with a compelling headline and a brief bio.
- **Projects Section**: Display your projects using cards or a grid layout. Each project should have a title, description, used tech and possibly a link to the live site or code repository.
- **Contact Section**: Provide your professional contact information.

## Setup Project

```bash
npx create-next-app portfolio
```

Edit `tailwind.config.js` to enable dark mode:

```javascript
module.exports = {
  darkMode: "class",
  // other configurations...
};
```

## ThemeContext and ThemeProvider

Create `ThemeContext.js` to manage theme and user preferences:

```javascript
import React, { createContext, useContext, useReducer } from "react";

const ThemeContext = createContext();

const initialState = {
  theme: "light",
  userPreferences: {
    fontSize: "medium",
    reduceAnimations: false,
  },
};

function themeReducer(state, action) {
  // your code here
}

export const ThemeProvider = ({ children }) => {
  // your code here
};

// Create and use your own hook instead of using useContext in the components
export const useTheme = () => useContext(ThemeContext);
```

## Applying the Theme Dynamically

In tailwind dark or light mode is set by adding or removing a class called `dark` in the root html tag. Use `ThemeContext` in `_app.js` to apply the theme class to the root element:

```javascript
import { useEffect } from "react";
import { ThemeProvider, useTheme } from "../contexts/ThemeContext";
import "../styles/globals.css";

function MyApp({ Component, pageProps }) {
  const { state } = useTheme();

  useEffect(() => {
    // Your code here. Add the dark class to the <html /> tag
    // with vanilla js.
  }, [state.theme]);

  return <Component {...pageProps} />;
}

export default ({ Component, pageProps }) => (
  <ThemeProvider>
    <MyApp Component={Component} pageProps={pageProps} />
  </ThemeProvider>
);
```

## Hand in Assignment

1. Initialize a git repository in your project if you haven't already.
2. Create a repository on GitHub and push your project there.
3. Submit the link to your GitHub repository on Canvas.

## :books: Reading List

- [Next.js Documentation](https://nextjs.org/docs)
- [React Context](https://reactjs.org/docs/context.html)
- [React useReducer Hook](https://reactjs.org/docs/hooks-reference.html#usereducer)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

## Creating the ThemeSwitcher and Handling User Preferences

Implement a component to toggle the theme and adjust user preferences:

## Using User Preferences in Components

Demonstrate using `userPreferences` in a component, adjusting styles based on the context state:

### :boom: Success!

Completing this assignment will significantly enhance your understanding of state management in React using `useReducer` and `Context`. You'll also gain more experience with Next.js, creating more dynamic and interactive web applications.

### :runner: Stretch goals

Add one or two more color schemes to your theme.
