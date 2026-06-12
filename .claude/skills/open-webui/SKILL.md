```markdown
# open-webui Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `open-webui` repository, a TypeScript codebase with no detected framework. You'll learn about file naming, import/export styles, commit message conventions, and how to write and run tests. This guide also provides suggested commands for common development workflows.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `userProfile.ts`, `apiClient.ts`

### Import Style
- Use **relative imports** for modules within the project.
  - Example:
    ```typescript
    import { fetchData } from './apiClient';
    ```

### Export Style
- Use **named exports** for functions, classes, and constants.
  - Example:
    ```typescript
    // In apiClient.ts
    export function fetchData() { ... }
    export const API_URL = '...';

    // In another file
    import { fetchData, API_URL } from './apiClient';
    ```

### Commit Messages
- Follow **conventional commit** format.
- Common prefix: `chore`
- Example:
  ```
  chore: update dependencies for security
  ```

## Workflows

### Commit Changes
**Trigger:** When making any code changes  
**Command:** `/commit-changes`

1. Make your code changes following the coding conventions.
2. Stage your changes:
   ```
   git add .
   ```
3. Write a conventional commit message, e.g.:
   ```
   git commit -m "chore: update user authentication logic"
   ```
4. Push your changes:
   ```
   git push
   ```

### Add a New Module
**Trigger:** When adding a new feature or utility  
**Command:** `/add-module`

1. Create a new file using camelCase, e.g. `newFeature.ts`.
2. Use named exports for all functions and constants.
   ```typescript
   export function newFeature() { ... }
   ```
3. Import the module using a relative path where needed.
   ```typescript
   import { newFeature } from './newFeature';
   ```
4. Write corresponding tests in a file named `newFeature.test.ts`.

### Write and Run Tests
**Trigger:** When adding or updating code  
**Command:** `/run-tests`

1. Create test files matching the pattern `*.test.*`, e.g. `apiClient.test.ts`.
2. Write tests for each exported function or class.
3. Run the tests using the project's test runner (framework unknown; check project documentation or package.json for scripts).
   ```
   npm test
   ```
   or
   ```
   yarn test
   ```

## Testing Patterns

- Test files are named with the pattern `*.test.*` (e.g., `userProfile.test.ts`).
- Each exported function or class should have corresponding tests.
- The specific testing framework is unknown; refer to project scripts or documentation for details.

**Example test file:**
```typescript
import { fetchData } from './apiClient';

describe('fetchData', () => {
  it('should return expected data', async () => {
    const data = await fetchData();
    expect(data).toBeDefined();
  });
});
```

## Commands
| Command         | Purpose                                     |
|-----------------|---------------------------------------------|
| /commit-changes | Commit code changes using conventions       |
| /add-module     | Add a new module following project patterns |
| /run-tests      | Run all tests in the repository             |
```