+++
title = 'How to Update with each new post'
date = 2025-04-13T19:42:58+02:00
draft = false
+++

To publish a new post on your Hugo website hosted via GitHub Pages, follow these steps:

---

## 📝 Step 1: Create a New Post
In your Hugo site's root directory, run

```bashhugo new posts/your-post-title.m
```

Replace `your-post-title` with a suitable filename for your post. This command creates a new Markdown file in the `content/posts/` directory

---

## ✏️ Step 2: Edit the Post Content

1.Open the newly created file in your text editor
2.Modify the front matter at the top of the file to set `draft: false` so the post will be published

   ```yaml
   ---
   title: "Your Post Title"
   date: 2025-04-13T20:18:39+02:00
   draft: false
   --
   ```


3.Add your content below the front matter

---

## 🔍 Step 3: Preview Locally (Optional)
To preview your site with the new pos:

```bas
hugo servr
```

Then, open `http://localhost:1313` in your web browser to view the sit.

---

## 🚀 Step 4: Deploy to GitHub Pages

. Stage all changs:

   ```bash
   git add .
   ```


. Commit the changs:

   ```bash
   git commit -m "Add new post: Your Post Title"
   ```


. Push to GitHb:

   ```bash
   git push
   ```


Your GitHub Actions workflow will automatically build and deploy the updated sie.

---

## 🌐 Step 5: Verify the Deployment
1. Navigate to your GitHub repositry.2. Click on the **Actions** tab to monitor the deployment workfow.3. Once the workflow completes successfully, visit your siteat:

   ```
   https://your-username.github.io/your-repository-name/
   ```

Replace `your-username` and `your-repository-name` with your actual GitHub username and repository nme.

--

By following these steps, your new post will be live on your Hugo-powered GitHub Pages webste. 