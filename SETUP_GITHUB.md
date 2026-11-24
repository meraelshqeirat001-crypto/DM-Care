# Create the independent GitHub repository

1. Sign in to GitHub and open https://github.com/new .
2. Set repository name to `DM-Care` (if available).
3. Choose **Public** if you want to use GitHub Pages on a free personal account, or choose Private if you do not need public Pages and your plan supports your intended publishing method.
4. Do not add a README, `.gitignore`, or license during repository creation; this ZIP already contains project files.
5. Create the repository.
6. On the new repository page choose **Add file → Upload files**.
7. Extract the ZIP on your device/computer, then upload the files and folders inside `DM-Care-project` (not the ZIP itself). Keep `public/index.html` in the `public` folder.
8. Commit the upload to the `main` branch.
9. For GitHub Pages, open **Settings → Pages**. Choose **Deploy from a branch**, select `main`, and select `/public` if the interface offers it. If `/public` is not offered, use the Firebase Hosting method in `SETUP_FIREBASE.md` instead; GitHub Pages commonly publishes from the root or `/docs`, not an arbitrary folder.
10. After deployment, open the Pages URL and complete the checklist in `TEST_CHECKLIST.md`.

**Keep DM-Care separate:** confirm the repository URL contains `/DM-Care` (or your chosen new repository name), not `/MedGuard-JO`.
