# NextJs
To build a complete web application with React from scratch, there are many important details you need to consider:

- Code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
You need to do production optimizations such as code splitting.
- You might want to statically pre-render some pages for performance and SEO. You might also want to use server-side rendering or client-side rendering.
- You might have to write some server-side code to connect your React app to your data store.


### Next.js: The React Framework
Enter Next.js, the React Framework. Next.js provides a solution to all of the above problems. But more importantly, it puts you and your team in the pit of success when building React applications.

### Create a Next.js app
To create a Next.js app, open your terminal, cd into the directory you’d like to create the app in, and run the following command:

`npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/learn-starter"`
Run the development server
You now have a new directory called nextjs-blog. Let’s cd into it:

`cd nextjs-blog`
Then, run the following command:

`npm run dev`


#  React context

### What is React context?
React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.


### When should you use React context?
React context is great when you are passing data that can be used in any component in your application.

These types of data include:

Theme data (like dark or light mode)
User data (the currently authenticated user)
Location-specific data (like user language or locale)
What problems does React context solve?
React context helps us avoid the problem of props drilling.

Props drilling is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.

As you can see, however, the direct children of App, such as Header, also have to pass the theme data down using props.
```
export default function App({ theme }) {
return (
    <>
    <Header theme={theme} />
    <Main theme={theme} />
    <Sidebar theme={theme} />
    <Footer theme={theme} />
    </>
);
}
```
```
function Header({ theme }) {
return (
    <>
    <User theme={theme} />
    <Login theme={theme} />
    <Menu theme={theme} />
    </>
);
}
```

### How do I use React context?
This means that we can create and use context directly by importing React in any React project.

There are four steps to using React context:

Create context using the createContext method.
Take your created context and wrap the context provider around your component tree.
Put any value you like on your context provider using the value prop.
Read that value within any component by using the context consumer.