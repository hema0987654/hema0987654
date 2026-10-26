# Setup guide

## 1. Create the profile repository

1. Confirm your GitHub username is `hema0987654`.
2. Create a **public** repository named exactly `hema0987654` (the repository name must match your username).
3. Put `README.md`, `assets/backend-header.svg`, and `.github/workflows/snake.yml` at the repository paths shown here.
4. In repository **Settings → Actions → General → Workflow permissions**, allow workflows to have read and write permissions to the repository contents. Save if you change it.
5. Commit and push to the `main` branch.

## 2. Run the snake workflow

1. Open the repository's **Actions** tab.
2. Select **Generate contribution snake**.
3. Click **Run workflow** and run it on `main`.
4. Wait for the run to finish successfully. It creates/updates the `output` branch with `github-snake.svg` and `github-snake-dark.svg`.
5. Open the `output` branch and verify both files exist. The README image URL expects this branch.

The workflow runs daily and after pushes to `main`. The first snake image will not exist until a successful workflow run. If the `output` branch already contains unrelated files, be aware the publishing action publishes the generated `dist` directory to that branch.

## 3. Replace placeholders

Search the README for `YOUR_` and replace:

- `YOUR_PUBLIC_EMAIL` — public contact email.
- `YOUR_LINKEDIN_URL` — actual LinkedIn profile URL, or remove those links if you do not want LinkedIn shown.
- `YOUR_PROJECT_1_URL`, `YOUR_PROJECT_1_REPO`, `YOUR_PROJECT_1_NAME` — first real repository URL, exact repo name, and title.
- `YOUR_PROJECT_2_URL`, `YOUR_PROJECT_2_REPO`, `YOUR_PROJECT_2_NAME` — second real repository details.

Update the username `hema0987654` everywhere if your profile username differs. The README includes links to third-party dynamic services; review their current availability and privacy policies before relying on them.

## 4. Test the profile

- Open the profile repository page and confirm the README is displayed.
- Click the header SVG in the repository and confirm it loads. SVG animation can behave differently in previews and browser tabs; if the animation is stripped or frozen by a viewer, keep the banner as a decorative static image rather than relying on it for meaning.
- Click the typing SVG and confirm the image service responds. If it is down, remove the image or use the service's demo to regenerate the URL.
- Open the statistics cards directly. Check that the username in each URL is correct. Third-party cards may be rate-limited, cached, or unavailable; they are not guaranteed uptime services.
- In Actions, confirm the snake job is green and the `output` branch contains both SVG files. Then hard-refresh the profile page.
- Validate the workflow by running it manually after every workflow edit.

## 5. Troubleshooting

### Snake workflow fails to push

- Check **Settings → Actions → General → Workflow permissions** and enable read/write contents permissions.
- Check that repository Actions are enabled and inspect the failed step's logs.
- If organization policy blocks write permissions, an owner must permit them.
- The workflow needs no personal access token; it uses the repository's `GITHUB_TOKEN`.

### Snake image is broken

- Verify the `output` branch exists and contains `github-snake.svg` and `github-snake-dark.svg` at its root.
- Confirm repository owner/name in the README image URLs.
- Open the raw SVG URL directly. A newly created branch or CDN may take a short time to become visible.
- If you change the output filenames, update both `srcset` paths in the README.

### Stats cards are blank or stale

- Open each card URL directly and confirm the username spelling.
- Public services may cache data, rate-limit requests, or have outages. Wait and retry, or remove a failed card rather than assuming its numbers are correct.
- The language card estimates language usage from repositories it can access; it does not measure skill level. Forks, private repositories, and excluded languages may affect results.

### Icons do not render

- Test the relevant `skillicons.dev` URL directly.
- Replace unavailable icons with text labels or remove the icon; do not let an icon imply expertise.

### Typing SVG is cut off

- Increase the `width` query parameter on the `readme-typing-svg.demolab.com` URL.
- URL-encode spaces and punctuation. Lines are separated by semicolons and spaces can be `+` or `%20`.

### Header animation is static

- Some SVG viewers sanitize or do not play SMIL animations. The banner remains readable without animation. Do not add JavaScript or scripts to the SVG; GitHub README embeds do not support arbitrary page scripts.
