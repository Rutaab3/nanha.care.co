# NanhaCare

NanhaCare is a static multi-page website focused on helping families in Pakistan discover trusted babysitters, browse child-related products, and access parenting resources.

## Project Overview

The site includes:

- A homepage introducing the NanhaCare brand and services
- A babysitters listing page with individual caregiver profile pages
- A products page featuring family and child essentials
- A blog/resources page with downloadable PDF guides
- Supporting pages such as about, contact, FAQ, pricing, training, privacy policy, terms of service, and sitemap

## Tech Stack

- HTML5
- Inline CSS and JavaScript
- Bootstrap 5 via CDN
- Font Awesome via CDN
- Google Fonts via CDN
- Chatling widget embed

This project does not currently use a build step or package manager. It can be served as a plain static site.

## Project Structure

```text
nanha.care.co/
|-- index.html
|-- about.html
|-- babysitters.html
|-- blog.html
|-- contact.html
|-- enroll.html
|-- faq.html
|-- pricing.html
|-- products.html
|-- training.html
|-- privacypolicy.html
|-- termsofservice.html
|-- sitemap.html
|-- data/
|   |-- babysitters.json
|   `-- products.json
|-- profiles/
|   |-- *.html
|   `-- images/
|-- images/
|-- pdfs/
`-- assets/
```

## Running Locally

Because this is a static site, you can preview it with any local web server.

Using Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

If you prefer, you can also use VS Code Live Server or any static hosting tool.

## Content Notes

- Main site pages live in the project root as `.html` files.
- Individual babysitter profile pages live in `profiles/`.
- Images are stored in `images/`, `profiles/images/`, and `assets/`.
- Downloadable parenting resources are stored in `pdfs/`.
- Structured content references are stored in `data/babysitters.json` and `data/products.json`.

## Editing Guidelines

- Keep relative links working across local preview and static hosting.
- Preserve the existing visual style unless a redesign is intentional.
- Optimize any new image assets before adding them.
- When updating caregiver, product, or article content, verify that linked images and PDFs exist at the referenced paths.
- Review pages in a browser after changes to catch layout issues, broken links, and missing assets.

## Deployment

The canonical URLs in the HTML point to a GitHub Pages-style deployment under `rutaab3.github.io/nanha.care.co`, so this project appears to be intended for static hosting.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for contribution guidelines.

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
