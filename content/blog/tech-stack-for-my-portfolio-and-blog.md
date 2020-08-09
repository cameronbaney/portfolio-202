---
title: Tech Stack for My Portfolio and Blog
---

## TL;DR

- **Framework**: [Nuxt](https://nuxtjs.org)
  - [Static site generation](https://nuxtjs.org/guides/concepts/static-site-generation)
  - Content created and maintained with [Nuxt Content](https://content.nuxtjs.org)
- **Design/CSS**: [Tailwind](https://tailwindcss.com)
- **Hosting and CI**: [Netlify](https://netlify.com)
- **Source Control**: [GitHub](https://github.com/cameronbaney/portfolio-2020)

## Thought process

I wanted to create my new portfolio with a stack that I was familiar with, but also didn't want to go too crazy. It's easy to get into the weeds when creating a site for yourself using the new shiny product or creating a complex system. Creating a personal site is a great opportunity to learn new technologies or products, but I didn't want to get too complicated. I kept all of my decisions and work around one major theme: ship fast and keep it simple.

## Decisions, decisions

Being a JavaScript engineer familiar with [Vue](https://vuejs.org) and [Nuxt](https://nuxtjs.org), I chose to use those with some of their newer features, and utility libraries. I also to use the new hotness (well not really that new anymore) [Jamstack](https://jamstack.org/)

[Nuxt Content](https://content.nuxtjs.org/) is one of those new features that I went with. With Nuxt Content, I can write my pages and blog posts using markdown, or go a more advanced route and use JSON. In addition, search, sorting and query building are native features of Nuxt Content so adding that to the site is simple.

I paired the ease of creating content with Nuxt Content with new features to Nuxt like full static site generation, component discovery, dynamic routes and crawling. With this setup, I can focus on the content of my site, and how it should look, rather than how it will be built, generated, and how everything works together.

## The paint job

Speaking of how things look, I decided to use the fantastic utility-first CSS library [Tailwind](https://tailwindcss.com/). Tailwind is great because it takes a lot of the thinking out of the way in terms of writing CSS, and allows me to focus on the design instead of implementation. I even chose to use colors from the [default color palette](https://tailwindcss.com/docs/customizing-colors/#default-color-palette) for my site. In the past, I lost way too much time figuring out what I wanted my color scheme to be. I was able to get out of my own way by leaning on Tailwind's palette to pick colors that were pretty much close to the scheme I had in mind already.

Since I was using Tailwind, and wanted to keep a pretty simple design, I chose not to use a component library like [Chakra UI](https://vue.chakra-ui.com/) or [Element](https://element.eleme.io). I love using component libraries when creating an app, but I didn't need anything complex for my site. My goals for the site are to present content, and didn't need any complex user interaction or input to accomplish that.

## Writing and maintaining the content

This is another area that I have overcomplicated for myself in the past. There are so many new and wonderful products out there like [Strapi](https://strapi.io/) or the newly announced [free-forever](https://twitter.com/contentful/status/1282667900013338626) tier of Contentful that can be used to write and maintain content. A personal project is a great way to learn some of these new products. However for this, Nuxt Content was perfect for my needs. I don't need a CMS or a complex system to integrate and write content. Keeping with the theme of shipping fast and keeping it simple, Nuxt Content checked all of the boxes for me.

## CI and hosting

Deciding on continuous integration and hosting was a no-brain. I already had my [repo on GitHub](https://github.com/cameronbaney/portfolio-2020), so I just needed to connect [Netlify](https://www.netlify.com/) to that. Netlify provides "The basics for personal projects, hobby sites, or experiments" for free. This includes a lot of advanced features like automated builds, deploying, site previews and hosting.

I'm pretty much using the default setup, with the exception of a custom build command `yarn generate`, which is simple to setup in Netlify. Every time code gets merged into `main`, Netlify will automatically build it using my custom command and deploy it to [https://cameronbaney.dev](cameronbaney.dev).

## Open source and develop in the open

I started my adventure in writing a new site by looking at various themes for [Nuxt](https://nuxtjs.org/themes), [Gridsome](https://gridsome.org/starters/), and even [Gatsby](https://www.gatsbyjs.org/docs/themes/). I had an idea of what I wanted my site to be, and none of these were satisfying all of those checkboxes. Ultimately, I wanted to create a site that I knew the setup, and to again, keep things simple.

A lot of these themes that I came across were pretty complex, and didn't necessarily use all of the stack I wanted to use. I wanted to create my own site tailored to my needs, but keeping it open enough for others to use. That's why I decided to [open source](https://github.com/cameronbaney/portfolio-2020) it, and develop it in the open. I hope that it is a valuable resource for engineers looking to do something similar, or that it may be a good starter for others looking for a simple portfolio.

## Let me hear it

If you use this repo to make a site of your own, I'd love to see what you did. Even if you have some questions or feedback, let me know on [https://twitter.com/cameronbaney](Twitter).

Cheers!
