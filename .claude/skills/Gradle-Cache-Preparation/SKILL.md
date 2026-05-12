```markdown
# Gradle-Cache-Preparation Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the development patterns and conventions used in the `Gradle-Cache-Preparation` repository, a TypeScript codebase designed to prepare and manage Gradle caches. The guide documents file organization, code style, commit conventions, and testing patterns to help contributors maintain consistency and quality.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `gradleCacheHelper.ts`

### Import Style
- Use **relative imports** for referencing other modules.
  - Example:
    ```typescript
    import { prepareCache } from './cacheUtils';
    ```

### Export Style
- Use **named exports** for functions, constants, and types.
  - Example:
    ```typescript
    export function prepareCache() { ... }
    export const CACHE_KEY = 'gradle-cache';
    ```

### Commit Patterns
- Commit messages are **freeform**, with no strict prefix requirements.
- Average commit message length is concise (~19 characters).

## Workflows

### Preparing the Gradle Cache
**Trigger:** When you need to set up or update the Gradle cache for a project.
**Command:** `/prepare-cache`

1. Ensure all dependencies are installed.
2. Run the cache preparation script:
    ```bash
    ts-node src/prepareCache.ts
    ```
3. Verify that the cache directory has been updated.

### Adding a New Utility Function
**Trigger:** When you need to add new helper logic to the codebase.
**Command:** `/add-utility`

1. Create a new file using camelCase in the appropriate directory.
2. Implement the function using named exports.
    ```typescript
    // src/newUtility.ts
    export function newUtility() { ... }
    ```
3. Import the function where needed using a relative path.
    ```typescript
    import { newUtility } from './newUtility';
    ```
4. Write a corresponding test file: `newUtility.test.ts`.

### Running Tests
**Trigger:** To validate code changes or before submitting a pull request.
**Command:** `/run-tests`

1. Identify test files matching the pattern `*.test.*`.
2. Run the test suite using your preferred TypeScript test runner (e.g., Jest, Mocha).
    ```bash
    npx jest
    ```
3. Review test results and fix any failures.

## Testing Patterns

- Test files follow the pattern: `*.test.*` (e.g., `cacheUtils.test.ts`).
- The testing framework is **unknown**; choose a common TypeScript-compatible runner (e.g., Jest).
- Place tests alongside or near the code they cover.
- Example test structure:
    ```typescript
    import { prepareCache } from './prepareCache';

    test('should prepare cache correctly', () => {
      // Arrange
      // Act
      // Assert
    });
    ```

## Commands

| Command         | Purpose                                    |
|-----------------|--------------------------------------------|
| /prepare-cache  | Prepare or update the Gradle cache         |
| /add-utility    | Add a new utility function to the codebase |
| /run-tests      | Run all test files in the repository       |
```
