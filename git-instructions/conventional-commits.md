# Conventional Commits: A Simple Guide

Think of Conventional Commits as a simple set of rules for how to write your commit messages. Instead of writing random messages like "fixed stuff" or "more work", you follow a clear pattern. This makes it much easier for everyone (including your future self!) to understand what changed and why.

## The Structure

A conventional commit message looks like this:

```
<type>[optional scope]: <description>

[optional body]

[optional footer]
```

Let's break it down:

### 1. **Type** - What kind of change is this? (Required)

This is the most important part. It's a short keyword that tells everyone the general category of your change.

*   **`feat`**: A new feature (e.g., adding a "dark mode" button).
*   **`fix`**: A bug fix (e.g., fixing a button that doesn't work).
*   **`docs`**: Changes to documentation only (e.g., writing this README).
*   **`style`**: Code style changes that don't affect meaning (e.g., adding spaces or semicolons).
*   **`refactor`**: A code change that neither fixes a bug nor adds a feature. It's about improving the code's structure.
*   **`perf`**: A change that improves performance.
*   **`test`**: Adding or fixing tests.
*   **`chore`**: Other changes that don't modify source code or tests (e.g., updating build scripts).

### 2. **Scope** - What part of the code is affected? (Optional)

This is a noun in parentheses that clarifies which part of the codebase you changed.

*   `feat(login): ...`
*   `fix(parser): ...`
*   `docs(readme): ...`

### 3. **Description** - What did you do? (Required)

A short, simple summary of the change, written in the present tense.

*   `feat: add user login functionality`
*   `fix: correct spelling errors in the main page`

### 4. **Body** - Why did you make this change? (Optional)

If your change is complex, you can add a more detailed explanation here. Explain the problem and how you solved it.

### 5. **Footer** - Any breaking changes or issue references? (Optional)

*   **Breaking Changes**: If your change breaks existing functionality, you MUST start the footer with `BREAKING CHANGE:`.
*   **Issue References**: If your commit relates to a GitHub issue, you can reference it here (e.g., `Closes #123`).

## Simple Examples

**A simple feature:**

```
feat: add a 'subscribe to newsletter' button
```

**A fix for a specific part of the app:**

```
fix(api): ensure user data is sent correctly
```

**A more complex change with a body and footer:**

```
feat: implement user authentication with email

This change introduces a new authentication system. Users can now sign up and log in using their email and a password. This was necessary because we previously had no way to track user accounts.

Closes #42
```

**A change that breaks things:**

```
refactor: rewrite the user profile page

BREAKING CHANGE: The user profile URL has changed from `/profile` to `/user/profile`. All links pointing to the old URL must be updated.
```

## Why Bother?

*   **Clarity:** Anyone can look at the commit history and understand what's happening.
*   **Automation:** Tools can automatically generate changelogs and determine version bumps (e.g., a `feat` might trigger a minor version bump, while a `BREAKING CHANGE` triggers a major one).
*   **Easier Reviews:** It helps your teammates understand your changes faster when they review your code.

	By following these simple rules, you make your project's history clean, understandable, and much more professional.