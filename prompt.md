# Simple Netlify site scaffold

Help a nontechnical person create a small, low-cost business website. Start by asking these questions in plain language, one at a time. Wait for each answer before asking the next:

1. What is your business name?
2. In a few sentences, what does your business do? Is there an existing website I can use to learn about it?
3. Would you like a Contact Us section?
4. Would you prefer one page or several pages?
5. What is the main thing you want visitors to do (for example, call, book, buy, or request a quote)?
6. Do you already have a logo, photos, brand colors, or text you want to use? (Optional.)

If they want several pages, ask which pages they need; examples are About Us, Locations, and Services. If they want a contact section, use a simple Netlify Forms contact form by default (name, email, and message), with the form present in the generated static HTML for Netlify to detect. Ask about public contact details only if needed, or use another contact method if they request one. If the main action is booking or shopping, ask for the URL of their existing external booking or store service. Ask follow-ups one at a time and only when needed to build the site. If they have no logo, offer to create a very basic SVG logo and matching `favicon.svg`; if they have a logo but no favicon, offer to make a favicon based on it. Keep this as one optional offer. Use sensible defaults for anything else, and briefly state those choices.

Create a simple static site. Link booking buttons to an external service such as Calendly and shopping buttons to an external store such as Shopify. Do not build booking, ecommerce, checkout, accounts, or a backend into this project. If an external URL is not available yet, use a clearly labeled placeholder and explain how to replace it. Use **pnpm**, **Tailwind CSS**, and **Netlify**. Use **fnm** to install and select a pinned current **Node.js LTS** version for building. Avoid paid services and unnecessary dependencies. Configure Netlify with the correct build command and publish directory. For additional pages, use URLs without trailing slashes by default (for example, `/about`, not `/about/`), and make navigation and Netlify routing consistent with those URLs. Create an **assets/** directory for images in the site's public/static files (for example, `public/assets/` with Vite), so the images are included in the Netlify deployment and have predictable URLs. If they accept the branding offer, place the logo and `favicon.svg` there, link the favicon from the site HTML, and make both easy to replace.

Configure pnpm in `pnpm-workspace.yaml` with `ignoreScripts: true` so install does not run package lifecycle scripts, and `minimumReleaseAge: 7200` so package versions must be at least five days old, including transitive dependencies. Set `minimumReleaseAgeStrict: true` and `minimumReleaseAgeIgnoreMissingTime: false` so installs fail rather than bypassing that age rule. Pin a pnpm version that supports these settings. Keep the site's own build and development commands explicit, and choose dependencies that work without approving install scripts or making age exceptions. Explain these choices in the docs.

Create a **.gitignore** suited to the generated project. Exclude dependencies, generated build output, local Netlify state, logs, local environment files, and editor or OS clutter; keep the pnpm lockfile, source files, and public assets tracked.

Create a **README.md** with the project overview, prerequisites, setup, useful commands, and simple Netlify deployment steps. Link to **docs/index.md** from the README. In **docs/**, make **index.md** link to every other document there. Include concise docs on the technology choices, useful commands, and where to add images. If using Netlify Forms, explain how to enable form detection in Netlify, where submissions appear, and how to test the form after deployment. Explain commands in plain language.

Make the scaffold build successfully. Then offer to run the asset build and start a local development server so the user can view the site while it is being built. Give the local URL and explain how to stop the server. Keep the site and instructions easy to edit.
