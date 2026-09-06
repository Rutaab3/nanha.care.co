<div align="center">

# NanhaCare

### Premier Early Childhood Care, Verified Babysitters, and Family Wellness Platform in Pakistan

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Bootstrap 5](https://img.shields.io/badge/Bootstrap_5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.style=for-the-badge.svg)](./LICENSE)
[![Status: Production Ready](https://img.shields.io/badge/Status-Production_Ready-success?style=for-the-badge)](# deployment)

---

<p align="center">
  <b>NanhaCare</b> is a static web platform tailored for Pakistani families. It connects parents with verified local caregivers, provides specialized child product catalogs, delivers expert parenting blogs and downloadable PDF guides, and offers enrollment options for professional caregiver training programs.
</p>

[Explore Features](#platform-features) &bull;
[Local Setup](#local-development-and-preview) &bull;
[System Architecture](#system-architecture) &bull;
[Data Schemas](#data-schemas) &bull;
[Contributing](./CONTRIBUTING.md)

</div>

---

## Table of Contents

- [Executive Summary](#executive-summary)
- [Platform Features](#platform-features)
- [System Architecture](#system-architecture)
- [Directory Structure](#directory-structure)
- [Tech Stack Overview](#tech-stack-overview)
- [Data Schemas](#data-schemas)
- [Local Development and Preview](#local-development-and-preview)
- [SEO and Schema Optimization](#seo-and-schema-optimization)
- [Deployment](#deployment)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Contributing](#contributing)
- [License](#license)

---

## Executive Summary

NanhaCare bridges the gap between parents seeking trustworthy childcare and professional caregivers across major cities in Pakistan, including Karachi, Lahore, and Islamabad. Built as a high-performance, lightweight static multi-page application, NanhaCare requires zero server-side build steps or complex runtime dependencies while delivering an interactive user experience powered by modern web technologies.

---

## Platform Features

| Module | Features & Capabilities | Target Audience |
| :--- | :--- | :--- |
| **Caregiver Directory** | Searchable directory featuring detailed caregiver profiles, hourly rates, verified badges, certifications, skills, and parent reviews. | Parents, Families |
| **Individual Profiles** | Dedicated profile pages displaying comprehensive qualifications, education, location, age specialization, and client feedback. | Parents, Recruiters |
| **Product Showcase** | Curated catalog of newborn and toddler essentials categorized by care, nutrition, safety, toys, and apparel. | Expectant & New Parents |
| **Knowledge Base** | Blog articles, developmental guides, parenting tips, and downloadable PDF resources. | General Community |
| **Caregiver Training** | Enrollment forms and curriculum details for professional babysitter certification and safety workshops. | Prospective Caregivers |
| **Interactive Support** | Embedded Chatling chatbot widget and SweetAlert2 form handling for real-time contact and enrollment requests. | Site Visitors |

---

## System Architecture

<details>
<summary><b>Click to expand System Architecture Details</b></summary>

<br>

NanhaCare follows a modular static asset architecture designed for fast loading times, search engine indexability, and straightforward maintenance.

```text
+-----------------------------------------------------------------------+
|                             USER BROWSER                              |
+-----------------------------------------------------------------------+
                                   |
         +-------------------------+-------------------------+
         |                         |                         |
         v                         v                         v
+------------------+     +-------------------+     +--------------------+
|  HTML5 Templates |     |  JSON Data Stores |     |  External CDNs     |
|  (Pages & Views) |     | (Caregivers/Items)|     | (Bootstrap/Swal2)  |
+------------------+     +-------------------+     +--------------------+
         |                         |                         |
         +-------------------------+-------------------------+
                                   |
                                   v
+-----------------------------------------------------------------------+
|                       DOM RENDERING & JS INTERACTION                  |
+-----------------------------------------------------------------------+
```

### Architecture Highlights
- **Decoupled Content**: Caregiver records and product information are maintained in structured JSON data files inside `data/`.
- **Zero Build Overhead**: Web browsers compile and render native ES6 JavaScript, HTML5, and CSS3 without requiring Babel, Webpack, or Vite bundling.
- **CDN-Accelerated Dependencies**: Frameworks like Bootstrap 5, Font Awesome, Google Fonts, and SweetAlert2 are loaded directly from trusted CDN providers for optimal caching.
- **Rich Snippet Structured Data**: JSON-LD scripts embedded across pages allow search engines to parse organizational information, reviews, and product metadata.

</details>

---

## Directory Structure

<details>
<summary><b>Click to expand Project Directory Tree</b></summary>

<br>

```text
nanha.care.co/
|-- index.html               # Main landing page featuring brand overview and highlights
|-- about.html               # Mission, vision, core values, and team information
|-- babysitters.html         # Caregiver directory listing page with filter tools
|-- products.html            # Family & child product catalog page
|-- blog.html                # Parenting articles, guides, and PDF downloads
|-- contact.html             # Customer inquiry form with SweetAlert2 integration
|-- enroll.html              # Caregiver training enrollment application form
|-- faq.html                 # Accordion-style frequently asked questions
|-- pricing.html             # Transparent tier pricing for services
|-- training.html            # Caregiver certification program syllabus
|-- privacypolicy.html       # Data protection and privacy notice
|-- termsofservice.html      # User agreement and operational terms
|-- sitemap.html             # HTML visual directory map
|-- sitemap.xml              # XML Search engine index sitemap
|-- robots.txt               # Crawler instructions
|-- llms.txt                 # AI and LLM context documentation
|-- 404.html                 # Custom page-not-found route
|-- CONTRIBUTING.md          # Project contribution policies
|-- LICENSE                  # MIT License grant
|-- data/
|   |-- babysitters.json     # Structured dataset for registered caregivers
|   `-- products.json        # Structured dataset for family products
|-- profiles/
|   |-- *.html               # Individual caregiver detailed profile pages
|   `-- images/              # Profile specific image assets
|-- assets/                  # Central CSS, JavaScript, and shared media files
|-- images/                  # Site banners, logos, product webp/png assets
`-- pdfs/                    # Downloadable parenting reference guides
```

</details>

---

## Tech Stack Overview

- **Frontend Core**: HTML5, ES6 JavaScript, CSS3
- **UI Framework**: Bootstrap 5.3 via CDN
- **Typography & Icons**: Font Awesome 6, Google Fonts (Poppins, Inter)
- **Interactive Modals & Alerts**: SweetAlert2
- **Chat Support**: Chatling Widget Integration
- **SEO & Metadata**: Schema.org JSON-LD, OpenGraph Tags, Canonical URLs

---

## Data Schemas

<details>
<summary><b>Click to view Data Schemas (`babysitters.json` & `products.json`)</b></summary>

<br>

### Caregiver Data Model (`data/babysitters.json`)

Each entry in `babysitters.json` follows a structured key-value format:

```json
{
  "babysitter1": {
    "name": "Zoya Ahmed",
    "image": "./images/zoya.webp",
    "location": "Islamabad, Pakistan",
    "experience_years": 3,
    "rate_per_hour": 450,
    "rating": 5.0,
    "reviews_count": 25,
    "quick_details": {
      "age": 26,
      "languages": ["Urdu", "English"],
      "marital_status": "Single",
      "smoker": false,
      "preferred_location": "At Home",
      "id": "NC-ISB-005",
      "verified": true
    },
    "certifications": [
      "CPR Certified",
      "First Aid Training",
      "Child Safety Course"
    ],
    "skills": [
      "Newborn Care",
      "Toddler Care",
      "Early Development"
    ],
    "about_me": [
      "Detailed caregiver background narrative..."
    ],
    "reviews": [
      {
        "parent": "Sara Khan",
        "location": "Islamabad",
        "rating": 5,
        "text": "Parent review feedback..."
      }
    ]
  }
}
```

### Product Data Model (`data/products.json`)

Each product entry defines item information used to render product cards and filters:

```json
{
  "products": [
    {
      "id": "prod-001",
      "name": "Newborn Essentials Set",
      "category": "Care & Hygiene",
      "price": 2500,
      "rating": 4.8,
      "image": "./images/Newborn Diapers.webp",
      "description": "Comprehensive care kit for infants."
    }
  ]
}
```

</details>

---

## Local Development and Preview

NanhaCare can be previewed locally using any standard static file web server.

<details open>
<summary><b>Method 1: Python HTTP Server (Recommended)</b></summary>

<br>

Run the following command in your terminal from the project root directory:

```bash
python -m http.server 8000
```

Access the platform at:

```text
http://localhost:8000/
```

</details>

<details>
<summary><b>Method 2: Node.js `serve` Package</b></summary>

<br>

```bash
npx serve . -p 8000
```

</details>

<details>
<summary><b>Method 3: VS Code Live Server</b></summary>

<br>

1. Open the project folder in Visual Studio Code.
2. Install the **Live Server** extension (`ms-vscode.live-server`).
3. Right-click `index.html` and select **Open with Live Server**.

</details>

---

## SEO and Schema Optimization

NanhaCare implements search engine optimization and accessibility best practices:

- **Structured Data**: Embedded JSON-LD schema objects provide search engines with rich metadata for `Organization`, `WebSite`, `LocalBusiness`, and `Product`.
- **Sitemap XML**: Fully configured `sitemap.xml` mapping all key routes and media endpoints.
- **Robots Directives**: Standardized `robots.txt` allowing indexing for compliant search engine crawlers.
- **LLM Transparency**: `llms.txt` file providing explicit context for modern AI systems and language models inspecting the platform.

---

## Deployment

The platform is designed for seamless deployment on static hosting platforms including:

- **GitHub Pages**
- **Vercel**
- **Netlify**
- **Cloudflare Pages**

Ensure relative link structures remain intact when deploying to custom domain endpoints or subdirectories.

---

## Frequently Asked Questions

<details>
<summary><b>Q: Does NanhaCare require Node.js or a build step to run?</b></summary>

<br>

No. NanhaCare is a pure static web project composed of HTML, CSS, JavaScript, and JSON data files. It runs natively in any modern web browser without transpilation or build tools.

</details>

<details>
<summary><b>Q: How are new caregivers added to the platform?</b></summary>

<br>

Caregivers can be added by creating a corresponding entry in `data/babysitters.json` and adding a matching profile page in `profiles/`.

</details>

<details>
<summary><b>Q: How are form submissions handled on contact and enrollment pages?</b></summary>

<br>

Form interactions use SweetAlert2 modal popups to validate user inputs client-side before providing submission confirmation feedback.

</details>

---

## Contributing

We welcome community contributions! Please review our guidelines in [CONTRIBUTING.md](./CONTRIBUTING.md) to learn how to propose feature additions, report issues, or submit pull requests.

---

## License

Distributed under the MIT License. See [LICENSE](./LICENSE) for full license details.
