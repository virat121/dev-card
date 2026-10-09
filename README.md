# My Dev Card

A one-page personal card you'll make your own and put live on the internet — using Git and GitHub.

## What you'll do

1. Fork this repo
2. Clone your fork to your laptop
3. Add your details
4. Commit and push
5. Turn on GitHub Pages and get a live link
6. Ship a dark mode using a branch

---

## Before you start

```bash
git --version                                   # should print a version number
git config --global user.name "Your Name"
git config --global user.email "you@email.com"  # same email as your GitHub account
```

---

## Part 1 · Make it yours and go live

### 1. Fork

Click **Fork** (top right of this page), then **Create fork**.
You now have your own copy at `github.com/<your-username>/dev-card`.

> Clone **your fork**, not this original repo. You can't push to a repo you don't own.

### 2. Clone

On your fork, click the green **Code** button and copy the HTTPS URL.

```bash
git clone https://github.com/<your-username>/dev-card.git
cd dev-card
```

### 3. Edit

Open the folder in VS Code (or any editor) and open `index.html`.
Every place you need to change is marked with a `✏️ EDIT` comment: your name, initials, bio, skills and links.
Save the file, then open it in your browser to check it.

### 4. Commit

```bash
git status                       # index.html shows as modified
git add index.html
git commit -m "Add my details to dev card"
```

### 5. Push

```bash
git push
```

Refresh your fork on GitHub. Your changes and your commit message are there.

> **First push asks you to sign in?**
> Windows: a browser window opens — sign in to GitHub.
> Mac/Linux: GitHub doesn't accept your account password here. Run `gh auth login` (GitHub CLI) or use a personal access token.

### 6. Go live

On your fork: **Settings → Pages → Build and deployment**
Source: **Deploy from a branch** · Branch: **main** · Folder: **/ (root)** → **Save**

Wait a minute or two, then open:

```
https://<your-username>.github.io/dev-card/
```

Open it on your phone. That's your site, on the internet. 🚀

---

## Part 2 · Ship a dark mode on a branch

```bash
git switch -c dark-mode
```

Open `style.css`. At the top you'll find five colour variables. Replace them with these (or pick your own):

```css
:root {
  --bg: #0f1420;
  --card: #1a2130;
  --text: #e8ecf3;
  --muted: #9aa4b6;
  --accent: #7aa7ff;
}
```

Commit it on the branch:

```bash
git add style.css
git commit -m "Change theme to dark mode"
```

Now switch back and look at `style.css` again:

```bash
git switch main
```

The colours are back to light. Your dark mode is safe on its own branch. Bring it in and ship it:

```bash
git merge dark-mode
git push
```

Refresh your live link in a minute — it's dark now.

---

## Done early? Try these

- Add a **Projects** section to `index.html` and push it as a new commit
- Run `git log --oneline` and read your project's history
- Make a change, run `git diff` to see it, then `git restore index.html` to undo it

## Commands you used today

| Command | What it does |
|---|---|
| `git clone <url>` | Copy a repo to your laptop |
| `git status` | See what changed |
| `git add <file>` | Stage changes |
| `git commit -m "..."` | Save a snapshot |
| `git push` | Send commits to GitHub |
| `git switch -c <name>` | Create and switch to a branch |
| `git switch <name>` | Switch branches |
| `git merge <branch>` | Bring a branch's work into the current one |
| `git log --oneline` | View history |

---

Made for a Git & GitHub session by [Leapo](https://leapo.in).
