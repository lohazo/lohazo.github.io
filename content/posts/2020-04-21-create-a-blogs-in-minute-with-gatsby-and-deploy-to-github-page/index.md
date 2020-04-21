---
title: Create a blogs in minute with gatsby and deploy to github page
author: Jang
date: '2020-04-21'
hero: images/maxresdefault.jpg
---
In this content we will going to build a full function cms:

1. admin for manager content
2. authentication so only you or authenticated user can create and publish a blogs
3. A beautiful front end

Q: where to store content and assets

A: github repository

### Step 1: Create a repository

Head over to GitHub and create a new repository named `username.github.io`, where username is your username (or organization name) on GitHub.

### Step 2: Clone the repository

Go to the folder where you want to store your project, and clone the new repository:

```shell
git clone https://github.com/username/username.github.io
```

```shell
gatsby new novela-site https://github.com/narative/gatsby-starter-novela
```

We will use the `master` branch for the `static` folder, the build result of gatsby. so we need to work on other `branch`, I will call it `develop`.

```shell
git checkout -b develop
```

Now we are ready for next step

### Step 3: Configuring siteMetadata

In order to configure the theme to properly generate the pages and meta tags you must add specific data to siteMetadata.

The fields that are unique to Novela are hero.heading, hero.maxWidth, and social.

Add your Site Metadata to the gatsby-config.js file.

```javascript
// gatsby-config.js

module.exports = {
  siteMetadata: {
    title: `Novela by Narative`,
    name: `Narative`,
    siteUrl: `https://gatsby-theme-novela.netlify.com`,
    description: `This is my description that will be used in the meta tags and important for search results`,

    // important to set the main text that appears in the hero
    hero: {
      heading: `Perspectives on technology, design and business from the team at Narative.`,
      maxWidth: 652,
    },
    social: [
      {
        name: `twitter`,
        url: `https://twitter.com/narative`,
      },
      {
        name: `github`,
        url: `https://github.com/narative`,
      },
    ],
  },
  plugins: ['@narative/gatsby-theme-novela'],
};
```

Fire up a browser and go to https://username.github.io.
