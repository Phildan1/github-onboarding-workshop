# GitHub Onboarding Guide

**Microsoft Naija Security User Group — Workshop Series · June 2026**

A step-by-step guide for security professionals getting started with GitHub — from account creation to secure repository management.

---

## Table of Contents

1. [Account Creation](#1-account-creation)
2. [Repository Setup](#2-repository-setup)
3. [Project Folder Structure](#3-project-folder-structure)
4. [Authoring a README with Markdown](#4-authoring-a-readme-with-markdown)
5. [Markdown Quick Reference](#5-markdown-quick-reference)
6. [Troubleshooting Common Pitfalls](#6-troubleshooting-common-pitfalls)
7. [Security Best Practices: Public vs. Private Repos](#7-security-best-practices-public-vs-private-repos)
8. [Hands-On Lab Exercises](#8-hands-on-lab-exercises)
9. [Resources & Next Steps](#9-resources--next-steps)

---

## 1. Account Creation

### Step 1 — Navigate to GitHub
Go to [https://github.com](https://github.com) and click **Sign up** in the top-right corner.

> **Security Note:** Use a browser with HTTPS enforced. Look for the padlock icon in the address bar.

---

### Step 2 — Enter Your Email Address
Enter the email address you want associated with your account. Use a professional or institutional address if possible — it will appear in your public commits.

> **Security Note:** Avoid addresses that reveal private information (e.g. birthdate, home address).

---

### Step 3 — Create a Strong Password
GitHub requires a minimum of **15 characters** OR **8 characters** with a number and lowercase letter. Use a passphrase:

```
correct-horse-battery-staple-9ja
```

> **Security Note:** Use a password manager (Bitwarden, 1Password, or Microsoft Authenticator). Never reuse passwords.

---

### Step 4 — Choose a Username
Pick a professional username — your name, initials, or handle. It appears in all repository URLs and commit history. You cannot easily change it later.

> **Security Note:** Avoid usernames that reveal your physical location, employer, or sensitive personal details.

---

### Step 5 — Verify Your Email
GitHub sends a verification email. Click the link inside it to activate your account. Check your spam folder if it does not arrive within 5 minutes.

> **Security Note:** Never click email verification links from untrusted sources. Always confirm the sender is `noreply@github.com`.

---

### Step 6 — Enable Two-Factor Authentication (2FA)

After logging in, go to **Settings → Password and Authentication → Enable two-factor authentication**.

Choose an authenticator app:
- Microsoft Authenticator *(recommended for MNSUG members)*
- Google Authenticator
- Authy

Save your recovery codes in a secure offline location.

> **Security Note — MANDATORY:** 2FA is required for all MNSUG members contributing to shared repositories. SMS-based 2FA is less secure — prefer an authenticator app.

> **IMPORTANT:** After enabling 2FA, GitHub displays one-time recovery codes. Download or print them and store securely. Losing these codes and your 2FA device locks you out permanently.

---

### Step 7 — Configure Your Profile
Go to **Settings → Profile**. Add your name, professional bio, MNSUG affiliation, and a profile photo.

> **Security Note:** Do not include your home address, phone number, or daily schedule in your public profile.

---

### Step 8 — Review Default Privacy Settings
Go to **Settings → Emails** and enable **Keep my email address private**. Go to **Settings → Privacy** to review who can see your activity.

> **Security Note:** Exposing your personal email in commits allows it to be harvested by scrapers. Always use the noreply GitHub address for public work.

---

## 2. Repository Setup

### Creating a New Repository

| Step | Action |
|------|--------|
| 1 | Click the **+** icon → **New repository** |
| 2 | Choose a descriptive lowercase name with hyphens |
| 3 | Write a short one-sentence description |
| 4 | Choose **Public** or **Private** (see Section 7) |
| 5 | Tick **Add a README file** |
| 6 | Select a `.gitignore` template |
| 7 | Choose a licence (MIT or Apache 2.0) |
| 8 | Click **Create repository** |

### Key Settings to Configure

| Setting | Location | Action |
|---------|----------|--------|
| Branch protection | Settings → Branches | Require PR reviews before merging |
| Collaborator access | Settings → Collaborators | Grant minimum needed access |
| Secret scanning | Settings → Security | Enable |
| Dependabot alerts | Settings → Security | Enable |

---

## 3. Project Folder Structure

### Creating Folders via the GitHub Web Interface

1. Click **Add file → Create new file**
2. Type the folder name followed by `/` — e.g. `docs/`
3. Type `.gitkeep` as the filename
4. Add a commit message and click **Commit new file**

### Recommended Structure

```
your-project/
├── README.md
├── SECURITY.md
├── CONTRIBUTING.md
├── LICENSE
├── .gitignore
├── docs/
│   └── runbooks/
├── policies/
├── templates/
└── references/
```

### What to Include in `SECURITY.md`

- Supported versions receiving security fixes
- How to report a vulnerability
- Expected response time
- What information reporters should include

---

## 4. Authoring a README with Markdown

### Anatomy of a Great Security Project README

| # | Section | Purpose |
|---|---------|---------|
| 1 | Project Title & Badges | H1 heading + status badges |
| 2 | Short Description | One or two sentences |
| 3 | Table of Contents | Internal-link TOC |
| 4 | Installation / Getting Started | Step-by-step prerequisites |
| 5 | Usage | Concrete examples with code blocks |
| 6 | Security Considerations | Sensitive config, known limitations |
| 7 | Contributing | Link to CONTRIBUTING.md |
| 8 | Licence | State clearly |
| 9 | Acknowledgements | Credit contributors and frameworks |

### Editing in the GitHub Web Interface

1. Click on `README.md` → click the **pencil icon**
2. Toggle between **Edit** and **Preview**
3. Add a descriptive commit message
4. Commit directly or create a new branch for review

---

## 5. Markdown Quick Reference

### Text Formatting

| Element | Syntax | Result |
|---------|--------|--------|
| Heading 1 | `# Title` | Large bold heading |
| Heading 2 | `## Section` | Medium bold heading |
| Bold | `**text**` | **text** |
| Italic | `*text*` | *text* |
| Inline code | `` `code` `` | `code` |
| Strikethrough | `~~text~~` | ~~text~~ |

### Code Block

````markdown
```python
def hello():
    print("Hello, MNSUG!")
```
````

### Lists & Tasks

```markdown
- Unordered item
1. Ordered item
- [x] Completed task
- [ ] Pending task
```

### Links & Tables

```markdown
[Link text](https://url.com)

| Col 1 | Col 2 |
|-------|-------|
| Cell  | Cell  |
```

### GitHub-Specific

| Syntax | Result |
|--------|--------|
| `@username` | Links to a GitHub profile |
| `#42` | Links to issue #42 |
| `> [!NOTE]` | Rendered note callout |
| `> [!WARNING]` | Rendered warning callout |

---

## 6. Troubleshooting Common Pitfalls

### T-01 — Cannot commit: "This branch is protected"
**Fix:** Create a new branch → open a Pull Request → get a reviewer → merge.

### T-02 — Markdown not rendering (shows raw text)
**Fix:** Ensure the file ends with `.md`. Check you are not on the raw URL.

### T-03 — Email not verified
**Fix:** Settings → Emails → Resend verification email.

### T-04 — File upload fails ("too large")
**Fix:** GitHub limits files to 25 MB via the web interface. Compress or use the CLI for larger files.

### T-05 — Lost 2FA access
**Fix:** Use recovery codes. If none, visit [github.com/sessions/two-factor-recovery](https://github.com/sessions/two-factor-recovery).

### T-06 — Repository shows empty after creation
**Fix:** Refresh the page. If still empty after 30 seconds, create the README manually.

### T-07 — "Commit changes" button is greyed out
**Fix:** Ensure you have made a change. Re-login if your session expired.

### T-08 — Secret accidentally committed
**Fix:** Immediately revoke the credential in the relevant service. Deleting the file does NOT remove it from Git history — contact your facilitator.

---

## 7. Security Best Practices: Public vs. Private Repos

### Decision Matrix

| Factor | Public | Private |
|--------|--------|---------|
| Who can view code | Anyone | Only invited collaborators |
| Search engine indexing | Yes | No |
| Secret scanning | Automatic | Requires Advanced Security |
| Forks | Anyone | Cannot be forked without access |
| Best for MNSUG | Workshop demos, open templates | Internal SOPs, sensitive research |

### Universal Practices

1. **Never commit secrets** — use environment variables or Azure Key Vault
2. **Use `.gitignore`** — add before first commit, include `.env`, `*.key`, `*.pem`
3. **Enable secret scanning** — automatic for public repos
4. **Enforce 2FA** — required for all org members
5. **Principle of least privilege** — Read access unless Write is needed
6. **Enable Dependabot** — Settings → Security → Dependabot alerts
7. **Review third-party apps** — Settings → Applications, remove unused apps

### MNSUG Repository Policy

| Content Type | Visibility |
|---|---|
| Workshop demos & public guides | Public |
| Security policy templates | Public |
| Internal SOPs and playbooks | Private |
| Incident response documentation | Private |
| Research / proof-of-concept tools | Private until disclosed |
| Azure Entra / M365 config guides | Private |
| CTF write-ups | Public (post-event only) |

---

## 8. Hands-On Lab Exercises

### Lab 1 — Create Your GitHub Account *(20 min)*
- [ ] Create account at github.com
- [ ] Verify email
- [ ] Enable 2FA with Microsoft Authenticator
- [ ] Save recovery codes
- [ ] Enable private email in commit settings
- [ ] Update profile with MNSUG affiliation

### Lab 2 — Create and Configure a Repository *(20 min)*
- [ ] Create repo named `ms9ja-[yourname]-workshop`
- [ ] Set visibility to Private
- [ ] Initialise with README, Python .gitignore, MIT licence
- [ ] Enable secret scanning and Dependabot
- [ ] Add branch protection rule (1 reviewer on main)
- [ ] Invite a neighbour as collaborator (Read access)

### Lab 3 — Build Your Folder Structure *(15 min)*
- [ ] Create `docs/` folder with `.gitkeep`
- [ ] Create `policies/` folder with `.gitkeep`
- [ ] Create `templates/` folder with `.gitkeep`
- [ ] Create `SECURITY.md` at the root
- [ ] Add supported versions and reporting contact to `SECURITY.md`

### Lab 4 — Write Your README *(25 min)*
- [ ] Add project title (H1 heading)
- [ ] Add one-paragraph description
- [ ] Add Table of Contents with internal links
- [ ] Add Usage section with a code block
- [ ] Add Security Considerations section
- [ ] Preview rendered Markdown before committing
- [ ] Commit with a meaningful message

### Lab 5 — Raise and Merge a Pull Request *(10 min)*
- [ ] Create branch `feature/add-incident-template`
- [ ] Create `templates/incident-report.md` on that branch
- [ ] Add H2 sections to the template
- [ ] Open Pull Request targeting `main`
- [ ] Get a neighbour to review and approve
- [ ] Merge the pull request

---

## 9. Resources & Next Steps

| Resource | Link |
|---|---|
| GitHub Docs — Getting Started | [docs.github.com/en/get-started](https://docs.github.com/en/get-started) |
| GitHub Docs — Markdown | [docs.github.com/en/get-started/writing-on-github](https://docs.github.com/en/get-started/writing-on-github) |
| GitHub Security Docs | [docs.github.com/en/code-security](https://docs.github.com/en/code-security) |
| GitHub Skills | [skills.github.com](https://skills.github.com) |
| Microsoft Security Learn | [learn.microsoft.com/security](https://learn.microsoft.com/en-us/security/) |
| Microsoft Entra Docs | [learn.microsoft.com/entra/identity](https://learn.microsoft.com/en-us/entra/identity/) |
| MITRE ATT&CK | [attack.mitre.org](https://attack.mitre.org) |
| NIST CSF | [nist.gov/cyberframework](https://www.nist.gov/cyberframework) |

### Next Steps After This Workshop

1. Complete **GitHub Skills: Introduction to GitHub** at [skills.github.com](https://skills.github.com)
2. Set up Git locally at [git-scm.com](https://git-scm.com)
3. Explore **GitHub Actions** for security automation
4. Join the MNSUG GitHub org — ask your facilitator for an invite
5. Complete **SC-900** (Microsoft Security Fundamentals)
6. Contribute to a community repo — review a PR or improve docs

---

*Microsoft Naija Security User Group · June 2026 · Workshop Use Only*
