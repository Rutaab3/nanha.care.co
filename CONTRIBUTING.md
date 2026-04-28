# Contributing to NanhaCare

Thanks for contributing to NanhaCare.

## Before You Start

- Review the existing page structure and naming conventions before making changes.
- Keep edits focused and easy to review.
- If you are changing content, confirm that all linked images, profile pages, and PDFs still resolve correctly.

## Recommended Workflow

1. Create a branch for your work.
2. Make small, focused changes.
3. Preview the site locally in a browser.
4. Check for broken links, missing assets, and layout regressions.
5. Submit your changes with a clear description.

## Local Preview

Run a simple static server from the project folder:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.

## Contribution Standards

- Use clear, consistent HTML formatting.
- Keep file and folder names predictable.
- Prefer relative paths for internal links and assets.
- Reuse existing styles and patterns unless the change is intentionally introducing a new direction.
- Keep external dependencies minimal.

## Content Changes

When updating content:

- Check spelling, grammar, and consistency of tone.
- Verify location names, profile information, prices, and resource titles carefully.
- Confirm that every new asset is added to the correct folder.
- Update related pages when a shared label, URL, or asset changes.

## Design and Frontend Changes

- Test changes on desktop and mobile viewport sizes.
- Avoid introducing layout shift, overflow, or broken spacing.
- Make sure buttons, navigation, and calls to action remain usable.
- Preserve accessibility basics such as meaningful alt text and readable contrast.

## Pull Request Checklist

- The site opens locally without errors.
- Updated pages render correctly.
- Links and image paths are valid.
- New assets are included in the repository.
- The change summary explains what was updated and why.

## Code of Collaboration

- Be respectful and constructive in feedback.
- Prefer clear explanations over broad rewrites.
- Raise questions early when a change affects shared structure or content.
