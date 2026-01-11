# real-User404-AI (@real-User404-AI)

This document describes **how to use** the GitHub bot **real-User404-AI**.  
It focuses purely on usage and behavior, not on implementation details.

---

## Overview

**real-User404-AI** is a GitHub Pull Request review bot.

- It listens to **PR comments**
- It activates when **mentioned**
- It analyzes the **diff of the Pull Request**
- It posts an **AI-generated review** as a PR comment

The bot is designed to act like a lightweight, on-demand code reviewer.

---

## How to Trigger the Bot

### Basic Usage

To trigger the bot, mention it in a **comment on a Pull Request**:

```text
@real-User404-AI please review this PR
````

As soon as the comment is posted, the bot will:

1. Detect the mention
2. Fetch the PR’s changed files
3. Analyze the diff
4. Reply with a review comment

---

## What the Bot Responds With

The bot posts **one comment per trigger** containing:

* A **high-level summary** of the changes
* **Potential bugs or risky patterns**
* **Concise suggestions** for improvement

The response is based solely on:

* The PR diff
* The text of the triggering comment

---

## Supported Context

* ✅ Pull Request comments
* ❌ Issue comments (non-PR)
* ❌ Commit comments
* ❌ Review submissions

Only **PR comments** are supported.

---

## Mention Rules

* The bot only reacts if it is **explicitly mentioned**
* The mention is **case-insensitive**
* Example valid mentions:

  * `@real-User404-AI`
  * `@Real-User404-AI`
  * `@real-user404-ai`

---

## One Response per Comment

Each comment can only trigger the bot **once**.

* Re-editing the same comment will **not** retrigger it
* Posting a **new comment** with a mention will trigger a new response

---

## Optional Restrictions (Configuration-Dependent)

Depending on how the bot is configured by the repository owner:

* The bot **may only respond to a specific GitHub user**
* The bot **may ignore mentions from others**

From a user perspective, this simply means:

> If the bot does not respond, it may be intentionally restricted.

---

## Diff Size Handling

* Large Pull Requests are supported
* If the diff is too large:

  * The input to the AI is **truncated**
  * The bot will still respond, but analysis may be partial

---

## Typical Use Cases

* Quick PR sanity checks
* Extra review feedback before requesting human review
* Spotting obvious bugs or risky patterns
* Getting a second opinion on refactors

---

## Example Interaction

**User comment:**

```text
@real-User404-AI can you review this for potential issues?
```

**Bot response (example):**

```text
Summary:
- Refactored authentication flow
- Added input validation

Potential Issues:
- Missing error handling in login handler

Suggestions:
- Consider adding unit tests for edge cases
```

---

## Limitations

* The bot does **not** approve or request changes formally
* It does **not** inline comments on specific lines
* It does **not** remember previous discussions
* It only reacts when mentioned

---

## Summary

**real-User404-AI** is an on-demand PR review assistant.

If you want feedback:

1. Open a Pull Request
2. Leave a comment
3. Mention `@real-User404-AI`

That’s it.
