# Wenting | Banking Data & AI Engineering Leadership Portfolio

A complete static professional portfolio aligned to a **Big Data AWS Senior Manager of Software Engineering, Consumer & Community Banking** position. The portfolio is an independent career demonstration and is **not** a JPMC website, and contains no bank systems or proprietary information.

## What's included

- Responsive personal portfolio with hero, quantified impact, interactive case-study filters, modal project details, architecture blueprint, leadership philosophy and contact section.
- Accessible, browser-based portfolio agent/chatbot that answers contextual questions about selected projects, leadership, AWS, Kafka/Kinesis/Flink, governance, reliability and deployment.
- No frameworks, backend, build process, third-party API keys or secrets required.
- Bitbucket Pipelines YAML for optional static validation.

## Local preview

Open `index.html` in any modern browser, or use a local server for a realistic preview:

```bash
python3 -m http.server 8000
```
Then visit http://localhost:8000 .

## Customize before publishing

1. Edit `assets/config.js` to replace `your.email@example.com`. Add LinkedIn/GitHub if you want; the template does not automatically display those URLs.
2. Edit the visible name, project claims and hero text in `index.html`. All metrics should be independently verified and appropriate for public release.
3. Edit agent answers and case study details in `assets/app.js` to match your experience.
4. Do not publish internal documents, bank information, credentials, source code or proprietary project details.
5. This portfolio loads optional Google Fonts from Google's CDN; if an entirely offline deployment is required, remove the `@import` from `assets/styles.css` (system font fallbacks are already configured).

## Deploy to Bitbucket Cloud static hosting

For the built-in Bitbucket Cloud website feature, create a **public** repository named exactly:

`YOUR_WORKSPACE_ID.bitbucket.io`

Place `index.html`, `assets/`, `README.md`, and optionally `bitbucket-pipelines.yml` at the **repository root** on the default branch. For example:

```bash
git init
git add .
git commit -m "Add banking engineering leadership portfolio"
git branch -M main
git remote add origin https://bitbucket.org/YOUR_WORKSPACE_ID/YOUR_WORKSPACE_ID.bitbucket.io.git
git push -u origin main
```

Your site should be served at `https://YOUR_WORKSPACE_ID.bitbucket.io/` (publication/cache timing can vary). If your Bitbucket account or workspace lacks static website hosting, use Bitbucket as the source repository and publish the same files to a static host such as Cloudflare Pages or Netlify, using no build command and `.` as the publish directory.

**Note:** This portfolio uses relative paths to work either at the site root or under a subpath on common static hosts. Hosting support and public repository requirements can change; check Atlassian's current Bitbucket Cloud static website documentation.

## About the assistant

The chatbot is a *working rule-based demo* in `assets/app.js`. It runs entirely client-side: no conversations are transmitted to a server, and it requires no API credentials. It's purpose-built to discuss this portfolio and is not a generative LLM.

### Production agent integration

A real LLM/agent implementation would need a separately deployed backend (e.g., API Gateway + Lambda + AWS Bedrock), identity/authentication, rate limiting, content and data controls, cost ceilings, monitoring, and an explicit allowlist of public portfolio material. Never call a private Bedrock API directly from a browser with embedded credentials. Bitbucket static hosting **cannot run a server-side API**.

## File map

```
index.html               Main website
assets/styles.css        Responsive visual design
assets/app.js            Filtering, modal case studies, offline chatbot
assets/config.js         Public identity/contact config
assets/favicon.svg       Site icon
bitbucket-pipelines.yml  Optional JavaScript and file validation
README.md                Instructions
```

## Verification

`node --check assets/app.js` and `node --check assets/config.js` validate JS syntax. Responsive layout is implemented via CSS media queries; browser/device QA is still recommended.
