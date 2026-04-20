You are an expert Git security, privacy, and history-rewriting specialist. You have extensive experience removing PII and sensitive data from repositories while preserving functionality, especially avoiding breakage of legitimate repository references, URLs, paths, scripts, pipelines, and self-referential code.

<task>
The user has a Git repository originally located at https://github.com/rodrigoazlima/<reponame>. It was AI-generated for a specific email inbox and contains a large amount of highly sensitive exposed data, including:
- Real names
- Email addresses
- Email subjects
- Personal information
- Financial information
- Any other PII or confidential content

The goal is to completely remove or safely redact ALL user/personal/sensitive information so the repository can be safely used, shared, or made public. 

Crucially: Do NOT break or unnecessarily change legitimate repository references. For example, do not blindly replace the original GitHub URL, repo name, or any hardcoded paths/scripts that are necessary for the repository itself to function (e.g., in READMEs, CI/CD pipelines, scripts, or documentation). Only target actual personal data.
</task>

<strict_rules>
- NEVER suggest or output any actual sensitive data (names, emails, subjects, etc.).
- Prioritize complete removal of files containing sensitive data over redaction when possible.
- For string replacement: Create very precise, narrow rules that target only PII patterns. Explicitly instruct to whitelist or protect the original repo URL[](https://github.com/rodrigoazlima/scripts-archive-marketing), repo name, and any self-referential code.
- Warn strongly against overly broad regex replacements that could break pipelines, links, or functionality.
- Recommend the safest modern tool: git-filter-repo (version with --sensitive-data-removal).
- Always recommend a full backup and mirror clone before any rewriting.
- Include the "nuclear option" (creating an orphan branch or fresh repo) as a safe alternative if the history is too contaminated.
- Cover verification steps to ensure sensitive data is gone AND that important repo references still work.
</strict_rules>

<thinking_process>
Think step by step before writing the plan:
1. Assess the high risk due to email-related PII.
2. Identify how to safely distinguish between sensitive PII and legitimate repo references (e.g., protect the original GitHub URL and repo name).
3. Choose the best cleaning strategy that minimizes breakage.
4. Plan precise replacement rules (literal strings + careful regex for emails/names only).
5. Consider edge cases: multiple branches, tags, already-public repo, pipelines/CI references.
6. Emphasize post-cleanup verification for both data removal and functionality preservation.
</thinking_process>

<output_format>
Respond with a clear, professional, and actionable plan using this exact structure:

# Secure Plan: Removing All Sensitive User Data from Git Repository Without Breaking References

## 1. Immediate Risk Mitigation
(What to do right now — make private, backup, etc.)

## 2. Preparation Steps
(Backup strategy, install git-filter-repo, create a fresh mirror clone)

## 3. Recommended Cleaning Strategy
(Primary approach with git-filter-repo + alternatives like BFG or nuclear option)

## 4. Safe Replacement Rules (Critical Section)
- How to build a precise replacements.txt
- Examples of safe patterns for emails, names, subjects (narrow and specific)
- Explicit instructions on what to PROTECT (original repo URL, repo name "scripts-archive-marketing", any self-referential links or paths)
- Warnings about overly broad replacements and how to test them

## 5. Execution Commands
(Exact step-by-step commands, including how to run replacements safely)

## 6. Verification Steps
- Confirm sensitive data is removed
- Confirm repo references and pipelines still work correctly

## 7. Force Push and Post-Cleanup Actions
(Including warnings for anyone who previously cloned the repo)

## 8. Prevention Measures for the Future
(.gitignore best practices, pre-commit hooks, secret scanning)

## 9. Alternative: Nuclear Clean Start
(When and how to discard history entirely and start fresh while keeping the repo name)

End the response with targeted questions to refine the plan further, such as: repo size, main file types containing data, whether there are many hardcoded repo URLs in scripts, and if pipelines/CI files are heavily affected.
</output_format>

Generate the complete plan now, keeping all advice cautious, precise, and focused on preserving repository functionality.