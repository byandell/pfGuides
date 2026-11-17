## Prompt

Explain how this repo is deployed as `https://atniclimate.github.io/TERRA/`. It may be that some components are not included in this repo.

## Response

### 1. Overview & Deployment Target

The repository is published to **`https://atniclimate.github.io/TERRA/`** via GitHub Pages.

This repository does not host a dynamic backend or the software engines of the nine applications; rather, it hosts a **static showcase and console ("command deck")** that tracks development status, releases, and architecture milestones across the Affiliated Tribes of Northwest Indians (ATNI) TERRA portfolio.

---

### 2. How the Deployment Pipeline Works

The site deployment is automated using GitHub Actions and GitHub Pages:

1. **Triggering Workflow**:
   Defined in [.github/workflows/pages.yml](file:///Users/brianyandell/Documents/GitHub/TERRA/.github/workflows/pages.yml#L4-L10):
   - Fires automatically on pushes to the `main` branch affecting `site/**` or the workflow file itself.
   - Can also be triggered manually via `workflow_dispatch`.

2. **Artifact Packaging (`path: site`)**:
   - The workflow uses `actions/upload-pages-artifact@v5` with the directive:

     ```yaml
     with:
       path: site
     ```

   - **Key Detail**: Only the contents of the `site/` folder are uploaded as the artifact root. The repository root files ([README.md](file:///Users/brianyandell/Documents/GitHub/TERRA/README.md), [LICENSE](file:///Users/brianyandell/Documents/GitHub/TERRA/LICENSE), `.gitignore`, etc.) are not published to the web.
   - Therefore, `site/index.html` serves as the entry point at `https://atniclimate.github.io/TERRA/`.

3. **Deployment Step**:
   - `actions/deploy-pages@v5` deploys the packaged artifact directly to the GitHub Pages environment (`github-pages`) under the `atniclimate` organization namespace.

4. **Jekyll Bypass (`.nojekyll`)**:
   - [site/.nojekyll](file:///Users/brianyandell/Documents/GitHub/TERRA/site/.nojekyll) is present in the artifact root. By default, GitHub Pages attempts to process repositories with Jekyll, which ignores directories starting with underscores. The `.nojekyll` file forces GitHub Pages to serve all files as static assets, ensuring paths like `site/iter/_kernel/` remain accessible.

5. **No Build Step**:
   - There are no npm scripts, Node dependencies, Webpack/Vite bundlers, or compilation commands. The site runs on pure HTML, CSS, client-side vanilla JavaScript, and self-hosted static assets.

---

### 3. What IS Included in This Repository

Everything inside the `site/` directory is tracked and deployed:

- **Primary Interface**: [site/index.html](file:///Users/brianyandell/Documents/GitHub/TERRA/site/index.html) (a standalone single-page application with "Field Station" and "Dossier" views, timeline controls, sovereignty framework matrices, and an embedded JSON data registry in `<script id="deck-data">`).
- **Iteration Reviews**: [site/iter/](file:///Users/brianyandell/Documents/GitHub/TERRA/site/iter) containing iteration mockups and comparison pages (`_kernel/`, `dossier/`, `dot-matrix/`, `field-station/`, and `ops-board/`).
- **Bundled Assets**:
  - **Self-Hosted Typography**: League Spartan and Poppins (`site/assets/fonts/`).
  - **Photography**: Over 130 art-directed, metadata-stripped Pacific Northwest landscape photographs (`site/assets/photos/`).
  - **GeoBase 3D Viewer**: A local offline CesiumJS runtime with pre-bundled sample terrain, NAIP imagery, and wind vector layers (`site/assets/geobase3d/`).
  - **Branding & Vector Assets**: ATNI marks, SVG icons, and NOAA ETOPO1 relief textures (`site/assets/img/`).

---

### 4. What is NOT Included in This Repository

As noted in [.gitignore](file:///Users/brianyandell/Documents/GitHub/TERRA/.gitignore#L1-L8) and the site's data records:

1. **The Source Code and Backends of the 9 Applications**:
   TERRA is a portfolio dashboard, not a monorepo. The actual applications reside in separate repositories or environments:
   - **Dynamic Drought Module (DDM)**: Deployed independently at `https://atniclimate.github.io/dynamic-drought-module/` (Source: `atniclimate/dynamic-drought-module`).
   - **Policy Sentinel**: Deployed independently at `https://atniclimate.github.io/policy-sentinel/` (Source: `atniclimate/policy-sentinel`).
   - **CAST / SHIELD**: Independent repository (`atniclimate/CAST`).
   - **Land Use Analyzer (LUA)**: Independent repository (`atniclimate/land-use-analyzer`).
   - **Community Navigator**: Independent repository (`atniclimate/community-connector`).
   - **ATNI GeoBase, TCR Policy Scanner, Plan Assessor, and ATNI ResIST**: Standalone desktop, local, or specialized analytical tooling.
   - **Backend Services & APIs**: There is no live database, server API, or active inter-application data pipeline hosted here (*"0 production data flows between them"*).

2. **External Standards & Frameworks**:
   - The Tiered Sovereign Data Framework (TSDF) documentation linked in the UI is hosted in its own documentation repository at `https://atniclimate.github.io/TieredSovereignDataFramework/`.

3. **Development & Planning Artifacts (Excluded by Git Allowlist)**:
   - [.gitignore](file:///Users/brianyandell/Documents/GitHub/TERRA/.gitignore) uses an explicit root allowlist (`/*` ignored except `.gitignore`, `site/`, `.github/`, `README.md`, `LICENSE*`).
   - Explicitly excluded and kept local by design:
     - Planning documents and design prompts
     - AI agent configurations and scratch files
     - Reference documentation and archive folders
     - Raw, uncompressed photo sources (`assets/pnw-source`)
