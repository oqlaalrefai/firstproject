# Dynamic Routes
- We want the URL for these pages to depend on the blog data, which means we need to use dynamic routes.
- Next.js allows you to statically generate pages with paths that depend on external data. This enables dynamic URLs in Next.js.
### How to Statically Generate Pages with Dynamic Routes
- We want each post to have the path /posts/<id>, where <id> is the name of the markdown file under the top-level posts directory.
- Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.

### Overview of the Steps
we’ll do it all on the next page.
  - we’ll create a page called `[id].js` under `pages/posts`. Pages that begin with `[` and end with `]` are dynamic routes in Next.js.
  - In `pages/posts/[id].js`, we’ll write code that will render a post page — just like other pages we’ve created.
  - We’ll export an async function called `getStaticPaths` from this page. In this function, we need to return a list of possible values for `id`.
  -  we need to implement `getStaticProps` again - this time, to fetch necessary data for the blog post with a given `id`. `getStaticProps` is given params, which contains `id` (because the file name is `[id].js`).
### Implement getStaticPaths
1. Create a file `[id].js` inside the `pages/posts` and remove `first-post.js` inside the `pages/posts`
2. open `pages/posts/[id].js` in your editor and paste the following code
```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}
```
3. open `lib/posts.js` and add the following `getAllPostIds` function at the bottom.
```
export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory)

  return fileNames.map(fileName => {
    return {
      params: {
        id: fileName.replace(/\.md$/, '')
      }
    }
  })
}
```
 It will return the list of file names (excluding `.md`) in the posts directory

4. we'll import the `getAllPostIds` function and use it inside `getStaticPaths`. Open `pages/posts/[id].js` and copy the following code above the exported `Post` component:
```
import { getAllPostIds } from '../../lib/posts'

export async function getStaticPaths() {
  const paths = getAllPostIds()
  return {
    paths,
    fallback: false
  }
}
```
### we still need to implement getStaticProps
We need to fetch necessary data to render the post with the given `id`.
1. open `lib/posts.js` again and add the following `getPostData` function at the bottom.
```
export function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`)
  const fileContents = fs.readFileSync(fullPath, 'utf8')

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents)

  // Combine the data with the id
  return {
    id,
    ...matterResult.data
  }
}
```
It will return the post data based on `id`:

2. open pages/posts/[id].js and replace this line:

`import { getAllPostIds } from '../../lib/posts'`
with the following code:
```
import { getAllPostIds, getPostData } from '../../lib/posts'

export async function getStaticProps({ params }) {
  const postData = getPostData(params.id)
  return {
    props: {
      postData
    }
  }
}
```

3. let's update the Post component to use postData. In pages/posts/[id].js replace the exported Post component with the following code:
```
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
    </Layout>
  )
}
```

### If you come across an error
make sure your files have the correct code

### Render Markdown
- To render markdown content, we’ll use the remark library.
`npm install remark remark-html`
- open lib/posts.js and add the following imports to the top of the file:
```
import { remark } from 'remark'
import html from 'remark-html'
```
- And update the getPostData() function in the same file as follows to use remark:
```
export async function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`)
  const fileContents = fs.readFileSync(fullPath, 'utf8')

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents)

  // Use remark to convert markdown into HTML string
  const processedContent = await remark()
    .use(html)
    .process(matterResult.content)
  const contentHtml = processedContent.toString()

  // Combine the data with the id and contentHtml
  return {
    id,
    contentHtml,
    ...matterResult.data
  }
}
```
- we need to update getStaticProps in pages/posts/[id].js to use await when calling getPostData:
```
export async function getStaticProps({ params }) {
  // Add the "await" keyword like this:
  const postData = await getPostData(params.id)
  // ...
}
```

- update the `Post` component in `pages/posts/[id].js` to render `contentHtml` using `dangerouslySetInnerHTML` :
```
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
      <br />
      <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
    </Layout>
  )
}
```

### Polishing the Post Page
1. Adding `title` to the Post Page
2. Formatting the Date
  - we’ll use the date-fns library. First, install it: `npm install date-fns`
  - create a file called components/date.js and add the following Date component:
```
import { parseISO, format } from 'date-fns'

export default function Date({ dateString }) {
  const date = parseISO(dateString)
  return <time dateTime={dateString}>{format(date, 'LLLL d, yyyy')}</time>
}
```
  - open `pages/posts/[id].js`, add an import for the `Date` component at the top of the file, and use it over `{postData.date}`:

### Adding CSS
using the file styles/utils.module.css we added before. Open pages/posts/[id].js, then add an import for the CSS file, and replace the Post component with the following code:
`import utilStyles from '../../styles/utils.module.css'`

### Polishing the Index Page
 We need to add links to each post page using the Link component.

1. Open `pages/index.js` and add the following imports at the top of the file for `Link` and `Date`:
```
import Link from 'next/link'
import Date from '../components/date'
```
2. near the bottom of the Home component in the same file, replace the li tag with the following:
```
<li className={utilStyles.listItem} key={id}>
  <Link href={`/posts/${id}`}>
    <a>{title}</a>
  </Link>
  <br />
  <small className={utilStyles.lightText}>
    <Date dateString={date} />
  </small>
</li>
```

### Dynamic Routes Details
1. **Fetch External API or Query Database**

2. **Development v.s. Production**
- development (npm run dev or yarn dev), getStaticPaths runs on every request.
- production, getStaticPaths runs at build time.

3. Fallback
- `fallback: false` from getStaticPaths:
any paths not returned by getStaticPaths will result in a 404 page.
- `fallback: true`, then the behavior of getStaticProps changes:
  - The paths returned from getStaticPaths will be rendered to HTML at build time.
  - The paths that have not been generated at build time will not result in a 404 page. Instead, Next.js will serve a “fallback” version of the page on the first request to such a path. 
  - In the background, Next.js will statically generate the requested path. Subsequent requests to the same path will serve the generated page, just like other pages pre-rendered at build time.
- If fallback is blocking, then new paths will be server-side rendered with getStaticProps, and cached for future requests so it only happens once per path.

4. Catch-all Routes
to catch all paths by adding three dots (`...`) inside the brackets. ex: `pages/posts/[...id].js` matches `/posts/a`, but also `/posts/a/b`, `/posts/a/b/c` and so on. 
- If you do this, in `getStaticPaths`, you must return an array as the value of the id `key`
- And `params.id` will be an array in `getStaticProps`:

5. Router
If you want to access the Next.js router, you can do so by importing the `useRouter` hook from `next/router`.
6. 404 Pages
To create a custom 404 page, create `pages/404.js`. This file is statically generated at build time.


# Deploying Your Next.js App
### Push to GitHub
  - On your personal GitHub account, create a new repository called nextjs-blog.
  - The repository can be public or private. You do not need to initialize it with a README or other files.
  - If you need help setting up your repo, take a look at this guide on GitHub.
  - If you haven’t initialized the git repository locally for your Next.js app, do so now.
  - Push the Next.js app to your GitHub repository.
### Deploy to Vercel
- **Vercel** is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database.
- The easiest way to deploy Next.js

1. Create a Vercel Account
2. Import your nextjs-blog repository
  - You’ll need to Install Vercel for GitHub. You can give it access to All Repositories.
  - Once you’ve installed Vercel, import nextjs-blog.
You can use default values for the following settings — no need to change anything.

- When it’s done, you’ll get deployment URLs. Click on one of the URLs and you should see the Next.js starter page live

### When you deploy your Next.js app to Vercel, the following happens by default:
- Pages that use Static Generation and assets (JS, CSS, images, fonts, etc) will automatically be served from the Vercel Edge Network, which is blazingly fast.
- Pages that use Server-Side Rendering and API routes will automatically become isolated Serverless Functions. This allows page rendering and API requests to scale infinitely.

### Vercel features 
- Custom Domains: Once deployed on Vercel, you can assign a custom domain to your Next.js app.
- Environment Variables: You can also set environment variables on Vercel. You can then use those environment variables in your Next.js app.
- Automatic HTTPS: HTTPS is enabled by default (including custom domains) and doesn't require extra configuration. We auto-renew SSL certificates

### Develop, Preview, Ship
We’ve just gone through the workflow we call DPS: Develop, Preview, and Ship.

- **Develop**: We’ve written code in Next.js and used the Next.js development server running to take advantage of its hot reloading feature.
- **Preview**: We’ve pushed changes to a branch on GitHub, and Vercel created a preview deployment that’s available via a URL. We can share this preview URL with others for feedback. In addition to doing code reviews, you can do deployment previews.
- **Ship**: We’ve merged the pull request to main to ship to production.







