
# Lab — Version Control with Git (Step-by-step)

> Goal: install/configure Git, put your code on GitHub, and publish it with GitHub Pages.

## 1) Check or install Git
- Open a terminal and run:
  ```bash
  git --version
  ```
- If not installed, download and install from https://git-scm.com/downloads

## 2) Configure your identity (global)
```bash
git config --global user.name "Your Name"
git config --global user.email you@example.com
```

## 3) Create a GitHub repository
1. Create/sign in to your account at https://github.com
2. Click **New** → Name it (e.g., `vue-js-labs`), choose **Public**, then **Create repository**.

## 4) Put your project under version control locally
If you created an empty repo on GitHub, clone it and copy your files in:

```bash
# replace the URL with the "Code → HTTPS" URL of your repo
git clone https://github.com/YOUR-USER/vue-js-labs.git
cd vue-js-labs

# copy your lab files into this folder (todo-plain.html, etc.)
# then stage and commit
git add .
git commit -m "Add starter lab demos"
git push origin main  # or 'master' if your default branch is named master
```

If your default branch is `master`, use `git push origin master` instead.

## 5) Publish with GitHub Pages
1. Go to your repo **Settings** → **Pages**.
2. Under **Source**, choose **Deploy from a branch**.
3. Select **Branch: main** and **/ (root)**, then **Save**.
4. Wait for the deployment to finish; GitHub will show a public URL like:
   `https://YOUR-USER.github.io/vue-js-labs/`
5. Make sure you have an `index.html` at the root, or visit individual files like
   `https://YOUR-USER.github.io/vue-js-labs/todo-vue.html`.

## 6) Routine workflow (commit, push, pull)
- After changes:
  ```bash
  git add .
  git commit -m "Describe what changed"
  git push
  ```
- To bring down changes from GitHub:
  ```bash
  git pull
  ```
