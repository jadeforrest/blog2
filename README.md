# Rubick.com Blog (note I've moved this repo to https://github.com/jadeforrest/blog

This repository contains the source code for [rubick.com](https://www.rubick.com), a personal blog built with [Astro](https://astro.build).

The blog features blog posts, a wiki section, full-text search, RSS feeds, and responsive design. Content is written in MDX (Markdown with React components) for flexibility and portability.

## Features

- **Modern Astro framework** with static site generation for fast performance and zero hosting costs
- **MDX content** - Write posts in Markdown with embedded React components
- **Full-text search** powered by Pagefind
- **Wiki section** for structured knowledge base content
- **Tag-based organization** for easy content discovery
- **RSS feed** for subscribers
- **Responsive design** that works on all devices
- **Syntax highlighting** with Shiki
- **Automatic sitemap generation**
- **SEO optimized** with OpenGraph tags

## Getting Started

### Prerequisites

- Node.js (v18 or higher recommended)
- npm

### Installation

```sh
npm install
```

### Development

Start the local development server at `localhost:4321`:

```sh
npm run dev
```

This automatically copies post images from `src/content/posts/` to `public/` before starting the dev server.

### Building

Build the production site to `./dist/`:

```sh
npm run build
```

This will:
1. Copy post images to the public directory
2. Build the Astro site
3. Generate the search index with Pagefind

### Preview

Preview your production build locally:

```sh
npm run preview
```

## Project Structure

```text
/
├── gatsby-blog/          # Legacy Gatsby blog (archived)
├── public/               # Static assets and copied post images
├── src/
│   ├── components/       # React and Astro components
│   ├── content/
│   │   ├── posts/        # Blog posts (YYYY-MM-DD--slug-name/index.mdx)
│   │   └── wiki/         # Wiki pages
│   ├── layouts/          # Astro layout components
│   ├── pages/            # Routes and page templates
│   ├── plugins/          # Custom remark plugins
│   └── theme/            # Theme configuration
├── astro.config.mjs      # Astro configuration
└── package.json
```

### Content Organization

**Blog Posts**: Located in `src/content/posts/`
- Directory naming convention: `YYYY-MM-DD--slug-name/index.mdx`
- Images stored alongside the post content
- Frontmatter includes title, tags, cover image, description, etc.

**Wiki Pages**: Located in `src/content/wiki/`
- Separate content collection for knowledge base articles
- Includes icon and description fields

## Commands

All commands are run from the root of the project:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**The code for this blog is MIT licensed** - you are free to use it to create your own blog.

**The content** (blog posts, wiki pages, images, and other written material) **is Copyright © Jade Rubick** and is not covered by the MIT license.

### Creating Your Own Blog

You are welcome to fork this repository and use the code to create your own blog:

1. **Fork and clone** this repository
2. **Install dependencies**: `npm install`
3. **Remove the existing content**:
   - Delete all directories in `src/content/posts/`
   - Delete all files in `src/content/wiki/`
   - Remove any associated images
4. **Customize the site**:
   - Update `astro.config.mjs` with your site URL and details
   - Modify `src/theme/` configuration files
   - Replace `public/favicon.ico` and other icons
   - Update OpenGraph images
5. **Add your content**:
   - Create your own blog posts in `src/content/posts/` following the naming convention
   - Add your own wiki pages to `src/content/wiki/` if desired
6. **Test locally**: `npm run dev`
7. **Build and deploy**: `npm run build` then deploy the `dist/` directory to any static host (Netlify, Vercel, Cloudflare Pages, etc.)

### Content Guidelines

- Blog post directories must follow the `YYYY-MM-DD--slug-name` format to be published
- Images should be placed in the same directory as your post's `index.mdx` file
- Use relative paths for images in posts (e.g., `./image.png`)
- Content schema is defined in `src/content/config.ts`

## History and Credits

This blog was originally built with [Gatsby](https://www.gatsbyjs.com/) and migrated to [Astro](https://astro.build) for improved performance and developer experience. The legacy Gatsby implementation is preserved in the `gatsby-blog/` directory.

### Gatsby Blog Origins

The original Gatsby blog was created by Baobab, building upon [Greg Lobinski's](https://github.com/greglobinski) excellent [hero-blog-starter](https://github.com/greglobinski/gatsby-starter-hero-blog/). Key improvements in that version included:

- Fixed draft post leaking into production
- Improved RSS feed with dates and proper filtering
- Redesigned contact form using Google Scripts
- Support for multiple tags per post
- Custom React components in Markdown
- Infinite scroll with graceful pagination fallback
- Refined design with tracedSVG image placeholders

### Attribution

- Original Gatsby starter by [Greg Lobinski](https://github.com/greglobinski)
- Gatsby blog implementation and improvements by Baobab
- Astro migration and current implementation by Jade Rubick
- Icons from [FontAwesome](https://fontawesome.com/) and [React Icons](https://react-icons.github.io/)

## Learn More

- [Astro Documentation](https://docs.astro.build)
- [Astro Discord](https://astro.build/chat)
- [Pagefind Documentation](https://pagefind.app/)
