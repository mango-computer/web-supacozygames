# Git Commit & Branching Best Practices

## ✍️ Commit Message Guidelines

Use clear, concise commit messages in **imperative mood** ("Add", "Fix", "Update") as if you're giving a command.

### ✔️ Format

```plaintext
<type>: Short summary in imperative mood (max 50 characters)

Optional longer body explaining the commit (wrap lines at 72 characters).
```

### ✔️ Examples

```bash
feat: Add animation to NPCs during idle state
fix: Correct layout issue on mobile devices
refactor: Simplify AI dialogue tree logic
```

### ✔️ Types (prefixes)

- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation only changes
- `style:` Formatting, missing semi colons, etc.
- `refactor:` Code change that neither fixes a bug nor adds a feature
- `test:` Adding or correcting tests
- `chore:` Build process or auxiliary tool changes

### ⚠️ Avoid

- Generic messages like `"update"`, `"fixes"`, or `"changes"`
- Descriptions in past tense: `"fixed layout"`, `"updated code"`

---

## 🚀 Branching Workflow

We follow a feature-branch based workflow inspired by Git Flow:

### 🌐 Main Branches

- `main`: Stable, production-ready code
- `develop`: Ongoing development, latest tested features

### 🎉 Feature Branches

For new features, bug fixes, or experiments:

```bash
git checkout develop
git pull
git checkout -b feat/ai-npc-dialogue
```

> Prefixes: `feat/`, `fix/`, `chore/`, `docs/`, etc.

### 🪜 Merging Feature Branches (No Fast-Forward)

To preserve history and context of the feature, always merge with `--no-ff`.

#### ✅ Example

```bash
git checkout develop
git pull
git merge --no-ff feat/ai-npc-dialogue -m "feat: Merge AI NPC dialogue feature"
git push origin develop
```

### 🔄 Syncing and Rebasing (Optional)

To keep your feature branch up to date before merging:

```bash
git checkout feat/ai-npc-dialogue
git fetch origin
git rebase origin/develop
```

---

## 🔐 Tips

- Always pull before starting work: `git pull origin develop`
- Push branches frequently to avoid data loss
- Write meaningful commits that document *why* a change happened

---

### 📄 Recommended Reading

- [Conventional Commits](https://www.conventionalcommits.org/)
- [Git Branching Model](https://nvie.com/posts/a-successful-git-branching-model/)

---

> By following these conventions, we keep our codebase clean, traceable, and collaborative for teams of all sizes.

