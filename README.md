# Olympus Design System

Static documentation for the Olympus mobile app design system.

This repository contains the current mobile design system documentation, including
tokens, components, screen patterns, audit notes, and a standalone static HTML
version published through GitHub Pages.

## Published Site

The GitHub Pages entry point is:

```text
docs/index.html
```

It is generated from the standalone design system file:

```text
mobile-app/components/Olympus Design System (standalone).html
```

When GitHub Pages is enabled for this repository, publish from:

```text
Branch: main
Folder: /docs
```

The public URL will be:

```text
https://<organization>.github.io/design-systems/
```

## Repository Structure

```text
docs/
  index.html                 GitHub Pages entry point
  .nojekyll                  Disables Jekyll processing

mobile-app/
  README.md                  Design system overview
  components/                Static component and token documentation
  guidelines/                Audits, inventories, and implementation notes
```

## Updating the Published Page

After changing the standalone HTML file, update the Pages entry point:

```bash
cp "mobile-app/components/Olympus Design System (standalone).html" docs/index.html
```

Then commit and push the change:

```bash
git add mobile-app/components/Olympus\ Design\ System\ \(standalone\).html docs/index.html
git commit -m "Update design system documentation"
git push
```

GitHub Pages may take a few minutes to publish the updated site.

## Access Control

The repository can be public while still restricting who can push changes.
Repository write access is controlled through organization teams and collaborators.
Protect the `main` branch to require pull requests and reviews before publishing
changes to the live Pages site.
