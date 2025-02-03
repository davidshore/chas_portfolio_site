# React Portfolio with Admin Page

In this assignment, you’ll build a portfolio website using Next.js, React, and Tailwind CSS, where users can:
✅ Display their projects on a portfolio page
✅ Add, edit, and delete projects via an admin page
✅ Save all data in Context so that updates in admin are reflected in portfolio
✅ Persist projects to a JSON string with local storage

You’ll use React Context for managing projects globally.

In the next course (Backend and devops), you will publish your portfolio on the web and we will store the JSON in a database.

## Building Your Portfolio Site

- **Hero Section**: Introduce yourself with a compelling headline and a brief bio.
- **Tech skills**: Display your current skills and experience.
- **Projects Section**: Display your projects using cards or a grid layout. Each project should have a title, description, used tech and possibly a link to the live site or code repository.
- **Contact Section**: Provide your professional contact information.

[Example portfolio in figma](https://www.figma.com/community/file/1116246660507537002)

## Setup Project

```bash
npx create-next-app portfolio
```

## Create context

We'll store the portfolio projects and tech skills in React Context.

Create `contexts/PortfolioContext.js`. Read from local storage if it exists, otherwise initialize an empty array for both projects and tech skills.

## Portfolio Page (Display Projects and Tech Skills)

Create `pages/index.js` and display the data you have in context together with your portfolio layout:

## Admin Page (Add/Edit/Delete Projects and Tech Skills)

Create `pages/admin.js`. All data should be saved to context and local storage.
Show Projects and Tech skills at the bottom of the page so that you see that they update correctly. The page should be secured with a login and password. In the next course we will store the password securely in a database.

### Starting code for username and password:

```
const [loggedIn, setLoggedIn] = useState(false);
const [credentials, setCredentials] = useState({ username: "", password: "" });

  function handleLogin(){
    if (credentials.username === "admin" && credentials.password === "password") {
      setLoggedIn(true);
    } else {
      alert("Invalid login");
    }
  };
```

## Hand in Assignment

1. Initialize a git repository in your project if you haven't already.
2. Create a repository on GitHub and push your project there.
3. Submit the link to your GitHub repository on Canvas.

## :books: Reading List

- [Next.js Documentation](https://nextjs.org/docs)
- [React Context](https://reactjs.org/docs/context.html)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

### :boom: Success!

Completing this assignment will significantly enhance your understanding of state management in React using `Context`. You'll also gain more experience with Next.js, creating more dynamic and interactive web applications.

### :runner: Stretch goals

Add dark mode and light mode to your portfolio.
