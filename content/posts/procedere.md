+++
title = 'Cheat Sheet for Initiating Hugo Website'
date = 2025-04-13T19:42:58+02:00
draft = false
+++

Certainly! Here's a concise cheat sheet summarizing the successful steps you took to create and deploy your first Hugo website using GitHub Pages:

---

## 🛠️ Hugo & GitHub Pages Deployment Cheat Sheet

### 1. **Install Hugo Extended**
Ensure you have the Extended version of Hugo, which is necessary for themes like Ananke that utilize SCSS/SASS

```bashsudo apt remove hugo
wget https://github.com/gohugoio/hugo/releases/download/v0.128.0/hugo_extended_0.128.0_Linux-64bit.deb
sudo dpkg -i hugo_extended_0.128.0_Linux-64bit.de
```


### 2. **Create a New Hugo Site**

```bashhugo new site my-hugo-site
cd my-hugo-sit
```


### 3. **Add a Theme (e.g., Ananke)**

```bashgit init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/anank
```

Update your configuration file (e.g., `config.toml` or `hugo.toml`) to include

```tomltheme = "ananke
```


### 4. **Create Content**

```bashhugo new posts/my-first-post.m
```

Edit the new post and set `draft: false` to make it public

### 5. **Preview Locally**

```bashhugo serve
```

Visit `http://localhost:1313` in your browser to view your site

### 6. **Initialize Git Repository**

```bashgit add .
git commit -m "Initial commit
```


### 7. **Create GitHub Repository**

-Log in to GitHub and create a new repository (e.g., `my-hugo-site`)
-Do **not** initialize with a README, `.gitignore`, or license

### 8. **Add Remote and Push**

```bashgit remote add origin https://github.com/your-username/my-hugo-site.git
git branch -M main
git push -u origin mai
```


### 9. **Set Up GitHub Actions for Deployment**
Create the following directory structure and workflow file

```bashmkdir -p .github/workflows
nano .github/workflows/hugo.ym
```

Paste the following content into `hugo.yml`

```yamlname: Deploy Hugo site to GitHub Pages

on:
  push:
    branches:
      - main
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.128.0
    steps:
      - name: Install Hugo
        run: |
          wget -O hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_Linux-64bit.deb
          sudo dpkg -i hugo.deb
      - name: Checkout repository
        uses: actions/checkout@v3
        with:
          submodules: true
          fetch-depth: 0
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v3
      - name: Build with Hugo
        run: hugo --gc --minify --baseURL "${{ steps.pages.outputs.base_url }}/"
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v1
        with:
          path: ./public

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```

Save and close the file

### 10. **Commit and Push Workflow**

```bashgit add .github/workflows/hugo.yml
git commit -m "Add GitHub Actions workflow for deployment"
git pus
```


### 11. **Configure GitHub Pages**

-Navigate to your repository on GitHub
-Go to **Settings** > **Pages**
-Under **Build and deployment**, set **Source** to **GitHub Actions**

### 12. **Access Your Deployed Site**
After the workflow completes, your site will be available at

```
https://your-username.github.io/my-hugo-site
```


---
This cheat sheet encapsulates the essential steps you followed to successfully create and deploy your Hugo website using GitHub PagesFor more detailed information, you can refer to the [official Hugo documentation on hosting with GitHub Pages](https://gohugo.io/host-and-deploy/host-on-github-pages/)

Feel free to reach out if you need further assistance or have additional questions! 