# Quizzle – before we start

## 1. Accounts (free)

- **GitHub** – create an account at [github.com](https://github.com), turn on two-factor login, and send your username to Christian so you can be invited to the repo.
- **Supabase** – sign up at [supabase.com](https://supabase.com) with your GitHub account, and you'll be invited to the project.
- **AI coding tool** – your choice. Start with GitHub Copilot Free, or use Claude Pro, ChatGPT Plus or Cursor if you prefer.
- **Groq** – sign up at [console.groq.com](https://console.groq.com) for a free API key. Only needed if you work on question generation.
- **Not needed:** Vercel. Christian owns the hosting.

## 2. Install

Open PowerShell and run:

```powershell
winget install --id Git.Git -e
winget install --id OpenJS.NodeJS.LTS -e
winget install --id Microsoft.VisualStudioCode -e
```

Close and reopen PowerShell, then:

- Install the VS Code extensions for ESLint and Prettier:

```powershell
code --install-extension dbaeumer.vscode-eslint
code --install-extension esbenp.prettier-vscode
```

- In VS Code, open **File → Preferences → Settings**, search for **Format On Save** and tick it.
- Tell Git who you are:

```powershell
git config --global user.name "Your Name"
git config --global user.email "the email you use on GitHub"
```

Cursor can be used instead of VS Code.

## 3. Check that it works

```powershell
git --version
node -v
npm -v
```

Each command should print a version number.

If PowerShell says *"running scripts is disabled on this system"*, run this once and try again:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

## 4. Once you're invited to the repo

Accept the invitation in the email from GitHub. Keep your code in a plain folder such as `C:\code` – not in OneDrive, which struggles with the thousands of files in `node_modules`.

```powershell
cd C:\code
git clone <repo-url>
cd quizzle
npm install
npm run dev
```

Then open http://localhost:3000. Stop the server with Ctrl+C. Open the project in VS Code with `code .` from the same folder.

The first time you push, a browser window opens to log in to GitHub.

## 5. Everyday workflow

```powershell
git checkout main
git pull                          # get the latest code
git checkout -b feature/my-change # new branch for your change
# ...write code...
git add .
git commit -m "Short description of the change"
git push -u origin feature/my-change
```

Then open the link that `git push` prints and create a pull request on GitHub.

## 6. Rules

- Never commit secrets. Keys go in `.env.local`, which Christian shares privately – never on WhatsApp or GitHub.
- Never push directly to `main`. Work in a branch and open a pull request.
- Stuck? Ask in the group – include a screenshot of the error.
