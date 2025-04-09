### 📘 `README.md`

```markdown
# 🚀 GitHub Pages Deployment with GitHub Actions

This project demonstrates how to automatically deploy a static HTML website to **GitHub Pages** using **GitHub Actions**.

> ✅ Whenever the `index.html` file is changed and pushed to the `main` branch, it is automatically deployed to GitHub Pages.

---

## 📂 Project Structure

```
gh-deployment-workflow/
│
├── index.html            # Main HTML file (Hello GitHub Actions!)
├── .github/
│   └── workflows/
│       └── deploy.yml    # GitHub Actions workflow file
└── README.md             # Project documentation
```

---

## 📄 What is happening?

- GitHub Actions is set up with a workflow file (`deploy.yml`)
- It watches for changes to the `index.html` file in the `main` branch
- When a change is detected, it:
  - Uses `peaceiris/actions-gh-pages` to push the contents to the `gh-pages` branch
  - Publishes the website at your GitHub Pages URL

---

## 🛠️ How to set it up?

1. Create a repository (e.g., `gh-deployment-workflow`)
2. Add an `index.html` file with your content
3. Create the folder `.github/workflows/` and add `deploy.yml` inside it
4. Add this to your `deploy.yml`:

```yaml
name: 🚀 Deploy to GitHub Pages

on:
  push:
    branches:
      - main
    paths:
      - index.html  # Only trigger when index.html is changed

jobs:
  push-to-pages:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repo and download to VM
      uses: actions/checkout@v4

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v4
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./
```

5. Go to `Settings > Actions > General` and set **workflow permissions** to:
   - ✅ “Read and write permissions”

6. Push everything to GitHub

---

## 🌐 Live Site

Visit your deployed website here:  
➡️ **[https://sachin-960.github.io/gh-deployment-workflow/](https://sachin-960.github.io/gh-deployment-workflow/)**

---

## 🧠 Learnings

- GitHub Actions
- Continuous Deployment (CD)
- GitHub Pages
- Workflow triggers and permissions

---

- Action used: [`peaceiris/actions-gh-pages`](https://github.com/peaceiris/actions-gh-pages)

---
This project is a part of [roadmap.sh](https://roadmap.sh/projects/github-actions-deployment-workflow) Devops Projects.
