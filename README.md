# Shivam Yadav | Developer Portfolio

Personal portfolio built as part of the **Future Interns Full Stack Web Development** internship (Task 1). It presents my background, skills, projects, credentials and a working contact form.

**Live site:** [https://portfolio-shivamyadav2007.netlify.app](https://portfolio-shivamyadav2007.netlify.app)
**Author:** [Shivam Yadav](https://github.com/shivam200717), B.Tech CSE, SRM IST

## Features

- Single-page layout: hero, resume (tabbed), skills, projects, credentials, contact
- Project cards with category filter, linking to each GitHub repo and live demo
- Dark / light mode
- Responsive layout built with Tailwind CSS
- Contact form that emails messages to my inbox (Web3Forms), with a hidden spam-trap field and error handling
- Print-friendly digital CV
- SEO: page title and description, Open Graph / Twitter tags, canonical URL, JSON-LD `Person` data, favicon, `robots.txt` and `sitemap.xml` generated at build time

## Tech stack

React 19, TypeScript, Vite, Tailwind CSS v4, lucide-react icons.

## Project structure

```
src/
  App.tsx            page layout and sections
  data/projects.ts   project list (edit this to add or change projects)
  lib/contact.ts     contact form submission logic
  index.css          global styles and theme helpers
public/              favicon and social preview image
vite.config.ts       Vite config plus SEO plugin (robots.txt, sitemap.xml)
```

## Setup (local)

Requires Node.js 20 or newer.

```bash
git clone https://github.com/shivam200717/<repo-name>.git
cd <repo-name>
npm install
cp .env.example .env.local
```

Edit `.env.local`:

| Variable | What it is |
| --- | --- |
| `VITE_WEB3FORMS_KEY` | Free access key from [web3forms.com](https://web3forms.com) (they email it to you). Messages from the form are delivered to that email. |
| `VITE_SITE_URL` | Your deployed URL without a trailing slash, e.g. `https://my-portfolio.vercel.app`. Used for canonical/OG tags and the sitemap. |

Then run:

```bash
npm run dev       # http://localhost:3000
npm run lint      # type check
npm run build     # production build in dist/
npm run preview   # serve the production build locally
```

Without `VITE_WEB3FORMS_KEY` the site still works, but the contact form shows a message pointing visitors to my email address.

## Deployment

### Vercel or Netlify (simplest)

1. Push this repo to GitHub.
2. Import it on Vercel or Netlify. Build command: `npm run build`, output directory: `dist`.
3. Add `VITE_WEB3FORMS_KEY` and `VITE_SITE_URL` as environment variables in the project settings.
4. Deploy. Add a custom domain under the project's domain settings if you have one, then update `VITE_SITE_URL` and redeploy.

### GitHub Pages

1. Set the two variables as repository secrets/variables and build with `npm run build`.
2. Publish the `dist/` folder (for example with a GitHub Actions Pages workflow or `gh-pages`). The Vite `base` is `./`, so it works under a `/<repo-name>/` sub-path.

## Customising

- Projects: edit `src/data/projects.ts`.
- Text, skills, resume tabs and credentials: edit the matching sections in `src/App.tsx`.
- Social preview image: replace `public/og-image.png` (1200x630).

## Roadmap

- Split `App.tsx` into smaller section components
- Add a downloadable PDF resume
- Add a blog section

## License

MIT. Feel free to take inspiration from the structure, but please use your own content.
