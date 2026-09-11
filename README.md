# Book Corner — GitHub-ready private-code PWA

## What this package is
A static PWA you can host from GitHub Pages or another HTTPS host.

- App code can live in a private GitHub repo.
- Your PDFs and reading data are **not uploaded to GitHub** by this app.
- PDFs are stored locally in your browser using IndexedDB.
- First launch creates one local username/password plus a separate Hidden Corner password.
- It requests persistent browser storage when supported.
- It works offline after the first successful load because of the service worker.
- It has no artificial book-count limit; practical storage is limited by browser/device quota.
- Export Backup downloads a JSON backup including your stored PDFs.
- Import Backup restores it.

## Important GitHub privacy note
A private repository keeps the repository code private to you/collaborators, but GitHub Pages availability/visibility depends on your GitHub plan and configuration. Do not put personal PDFs in the repository.

## Quick deployment
1. Create a new GitHub repository and set visibility to PRIVATE.
2. Upload these three files to the root:
   - index.html
   - manifest.webmanifest
   - sw.js
3. Commit them.
4. If your GitHub plan supports Pages for the repository, enable Pages in Settings → Pages.
5. Open the Pages URL once while online.
6. Bookmark it or use the browser's Install option if offered.

## Data model
GitHub hosts code only.
Browser IndexedDB holds:
- PDFs
- book titles/authors
- hidden library
- local login hashes
- settings

## Limits
This is not cloud sync. Your library is per browser/profile/device unless you export a backup and import it elsewhere.
Clearing the site's browser data can delete the library.
