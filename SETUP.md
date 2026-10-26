# Setup instructions

1. Open your profile repository: https://github.com/hema0987654/hema0987654
2. Replace the contents of `README.md` with the included `README.md`.
3. Add `.github/workflows/snake.yml` using the included workflow file.
4. Commit the changes to the default branch (usually `main`).
5. Open the repository's **Actions** tab and run **Generate contribution snake** once with **Run workflow**.
6. If the workflow fails, open its log and check that Actions are enabled and the workflow has permission to write repository contents. In **Settings → Actions → General → Workflow permissions**, allow read and write permissions if your repository settings require it.
7. After a successful run, the workflow creates/updates the `output` branch. The snake should then appear in the README after GitHub refreshes the image.

## Notes
- This package does not push changes to your GitHub account; upload/commit these files yourself.
- The animated header and typing animation use external services, so they depend on those services being available.
- GitHub README files do not run custom JavaScript or CSS. Use animated SVG/GIF images for motion.
- The featured repository cards are optional. Add them only after choosing real projects and confirming their names.
- If you want a custom illustrated avatar, upload the generated image to your repository (for example, `assets/avatar.png`) and add it to your profile or account avatar settings. Image generation failed in this conversation, so no avatar image is included in this package.
