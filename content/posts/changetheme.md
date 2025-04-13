+++
title = 'Change Theme in Hugo'
date = 2025-04-13T19:42:58+02:00
draft = false
+++

To change or add a new theme to your Hugo site, follow these steps:

---

### 🎨 Step 1: Choose a New Theme
Browse the [Hugo Themes](https://themes.gohugo.io/) directory to select a theme that suits your needsEnsure that the theme is compatible with your Hugo version and has the features you desire

---

### 📁 Step 2: Add the New Theme
Navigate to your Hugo site's root directory and add the new theme as a Git submodul:

```bas
git submodule add https://github.com/username/theme-repo.git themes/theme-nae
```

Replace `https://github.com/username/theme-repo.git` with the repository URL of your chosen theme and `theme-name` with the desired directory name for the them.

---

### ⚙️ Step 3: Update Configuration
Edit your site's configuration file (`config.toml`, `config.yaml`, or `hugo.toml`) to set the new them:

For `config.toml`:

```tom
theme = "theme-nam"
```


For `config.yaml`:

```yam
theme: theme-nae
```

Ensure that `theme-name` matches the directory name of the new theme in your `themes/` folde.

---

### 🧪 Step 4: Test the New Them

Run the Hugo development server to preview your site with the new thee:

```bah
hugo serer
```


Open `http://localhost:1313` in your web browser to view the changs.

---

### 🧹 Step 5: Remove the Old Theme (Optiona)

If you no longer need the previous theme, you can removeit:

```bsh
git submodule deinit themes/old-theme-name
git rm themes/old-theme-name
rm -rf .git/modules/themes/old-theme-ame
```

Replace `old-theme-name` with the directory name of the theme you wish to remve.

---

### 🚀 Step 6: Deploy the Updated Ste

After confirming that the new theme works as expected, commit your changes and push them to your reposiory:

```ash
git add .
git commit -m "Switched to new theme: theme-name"
gitpush
``


Your deployment pipeline (e.g., GitHub Actions) will handle rebuilding and deploying your site with the new teme.

---

**Not:** Some themes come with an `exampleSite` directory containing sample content and configurain. You can refer to these examples to understand how to structure your content and configure the theme effectiely.

If you need assistance customizing the new theme or encounter any issues, feel free to ask! 