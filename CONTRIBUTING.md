# Contributing Guidelines

Thank you for your interest in contributing to NanhaCare! We welcome community participation to enhance early childhood care resources, caregiver directory tools, and family support features across Pakistan.

---

## Core Contributors Roster

| Name | Contact Email | Role |
| :--- | :--- | :--- |
| Muhammad Rutaab Ali | [rutaabali3@gmail.com](mailto:rutaabali3@gmail.com) | Project Lead & Maintainer |
| Syed Muhammed Faraz | [muhammedfaraz875@gmail.com](mailto:muhammedfaraz875@gmail.com) | Core Developer |
| Ahad Mirza | [ahadmirza1604@gmail.com](mailto:ahadmirza1604@gmail.com) | Core Developer |

---

## Code of Conduct

We are committed to providing a welcoming, inclusive, and professional environment for all contributors regardless of background or level of experience. Please treat all community members with respect and professional courtesy.

---

## Contribution Workflow

To submit changes or new features to NanhaCare, follow this pull request process:

1. **Fork the Repository**: Create a personal copy of the repository on GitHub.
2. **Clone your Fork**:
   ```bash
   git clone https://github.com/your-username/nanha.care.co.git
   cd nanha.care.co
   ```
3. **Create a Feature Branch**:
   ```bash
   git checkout -b feature/descriptive-feature-name
   ```
4. **Make Changes and Test Locally**:
   - Preview changes using a local web server (`python -m http.server 8000`).
   - Verify layout responsiveness across desktop and mobile screen sizes.
   - Test external links, assets, and modal interactions.
5. **Commit Your Changes**:
   Follow conventional commit messaging:
   ```bash
   git commit -m "feat: add filter options to babysitters directory"
   ```
6. **Push to Your Branch**:
   ```bash
   git push origin feature/descriptive-feature-name
   ```
7. **Submit a Pull Request**:
   - Open a PR against the `main` branch of the official repository.
   - Provide a clear summary of your changes, motivation, and verification steps.

---

## Coding and Asset Guidelines

- **HTML & Formatting**: Keep HTML clean, semantic, and well-indented. Ensure meta tags and canonical URLs are preserved.
- **Data Synchronization**: When adding a caregiver or product, update `data/babysitters.json` or `data/products.json` and ensure associated images exist in `images/` or `profiles/images/`.
- **Image Assets**: Optimize images prior to committing (prefer `.webp` format for standard assets).
- **Zero Build Requirement**: Do not introduce mandatory build tools or bundlers without maintainer approval.
- **No Emojis Policy**: Maintain professional documentation formatting without using emojis in markdown files or commit messages.

---

## Reporting Issues and Suggestions

If you discover a bug or wish to suggest a new platform feature:

1. Check existing repository issues to prevent duplicate reports.
2. Open a new Issue providing a clear title, description of the problem or proposal, steps to reproduce, and expected behavior.
