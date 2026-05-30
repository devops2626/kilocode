```markdown
# kilocode Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill introduces the core development patterns and workflows used in the `kilocode` TypeScript codebase. It covers file naming, import/export conventions, commit practices, changelog management, and testing patterns. By following these guidelines, contributors can ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming

- Use **kebab-case** for all file names.
  - **Example:**  
    ```
    user-profile.ts
    data-fetcher.test.ts
    ```

### Import Style

- Use **relative imports** within the codebase.
  - **Example:**
    ```typescript
    import { fetchData } from './utils/fetch-data';
    ```

### Export Style

- Use **named exports** for all modules.
  - **Example:**
    ```typescript
    // utils/math.ts
    export function add(a: number, b: number): number {
      return a + b;
    }
    ```

    ```typescript
    import { add } from './utils/math';
    ```

### Commit Patterns

- Mixed commit types, commonly using prefixes like `fix` and `chore`.
- Commit messages are concise, averaging 57 characters.
  - **Example:**
    ```
    fix: correct typo in user-profile component
    chore: update dependencies in package.json
    ```

## Workflows

### Changelog Update and Backfill

**Trigger:** When documenting new changes or backfilling missing changelog entries for releases  
**Command:** `/update-changelog`

1. **Add or update** one or more `.changeset/*.md` files describing the changes.
2. **Update** the corresponding `packages/*/CHANGELOG.md` files with new entries.

**Example:**

- Create a new changeset:
  ```
  .changeset/awesome-feature-added.md
  ```
- Edit the package changelog:
  ```
  packages/core/CHANGELOG.md
  ```

### Enforce Changelog on Publish

**Trigger:** When ensuring that publishing is blocked unless changelog updates are present  
**Command:** `/require-changelog-for-publish`

1. **Add or update** a relevant `.changeset/*.md` file for your changes.
2. **Modify** `script/publish.ts` to enforce that changelog requirements are met before publishing.

**Example:**

- Add a changeset file:
  ```
  .changeset/fix-bug-in-parser.md
  ```
- Ensure `script/publish.ts` checks for changeset presence before proceeding.

## Testing Patterns

- Test files follow the `*.test.*` naming convention.
  - **Example:**  
    ```
    utils/math.test.ts
    ```
- The testing framework is **unknown**; inspect test files for further details.
- Place test files alongside the code they test or in a dedicated test directory.

**Example Test File:**
```typescript
// utils/math.test.ts
import { add } from './math';

test('add returns the sum of two numbers', () => {
  expect(add(2, 3)).toBe(5);
});
```

## Commands

| Command                        | Purpose                                                        |
|--------------------------------|----------------------------------------------------------------|
| /update-changelog              | Add or backfill changelog entries for new or past changes      |
| /require-changelog-for-publish | Enforce changelog presence before allowing package publishing  |
```
