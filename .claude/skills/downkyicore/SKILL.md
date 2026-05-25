```markdown
# downkyicore Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides a comprehensive guide to contributing to the `downkyicore` C# codebase. It covers coding conventions, commit patterns, and the primary workflows used for releases, dependency updates, bug fixes, settings management, and CI/CD pipeline changes. The guide is designed for developers seeking to maintain consistency and efficiency when working on this project.

## Coding Conventions

- **File Naming:**  
  Use PascalCase for all file names.  
  _Example:_  
  ```
  SettingsManager.Basic.cs
  AppInfo.cs
  ClipboardListener.cs
  ```

- **Import Style:**  
  Use relative imports within the project.  
  _Example:_  
  ```csharp
  using DownKyi.Core.Settings;
  using DownKyi.Core.BiliApi.WebClient;
  ```

- **Export Style:**  
  Use named exports for classes and members.  
  _Example:_  
  ```csharp
  public class SettingsManager
  {
      public static void LoadSettings() { ... }
  }
  ```

- **Commit Messages:**  
  Follow [Conventional Commits](https://www.conventionalcommits.org/).  
  Prefixes: `fix:`, `feat:`, `chore:`, `refactor:`  
  _Example:_  
  ```
  fix: correct login token refresh logic
  feat: add dark mode toggle to settings
  chore: update Avalonia to 11.0.0
  refactor: split download service logic
  ```

## Workflows

### Release Version Bump
**Trigger:** When preparing for a new release version  
**Command:** `/release`

1. Update `CHANGELOG.md` with the new changes.
2. Update `DownKyi/Models/AppInfo.cs` with the new version information.
   ```csharp
   public static string Version => "1.2.3";
   ```
3. Update `script/macos/Info.plist` for macOS packaging.
4. Update `version.txt` with the new version number.
5. Commit changes with a relevant message, e.g., `chore: bump version to 1.2.3`.

---

### Avalonia Dependency Update
**Trigger:** When upgrading the Avalonia UI library version  
**Command:** `/upgrade-avalonia`

1. Update `Directory.Packages.props` with the new Avalonia version.
   ```xml
   <PackageVersion Include="Avalonia" Version="11.0.0" />
   ```
2. Optionally update `README.md` or other documentation to reflect the new version.
3. Commit with a message like `chore: upgrade Avalonia to 11.0.0`.

---

### Fix Bug / Single Feature
**Trigger:** When a bug is found in a specific feature or utility  
**Command:** `/bugfix`

1. Identify the problematic file(s), e.g., `LoginHelper.cs`, `WebClient.cs`.
2. Apply the fix or optimization.
   ```csharp
   // Example fix
   if (token.IsExpired())
   {
       RefreshToken();
   }
   ```
3. Commit with a `fix:` message, e.g., `fix: handle expired login tokens`.

---

### Settings Manager Update
**Trigger:** When changing or optimizing settings logic or adding new settings  
**Command:** `/update-settings`

1. Edit one or more `SettingsManager.*.cs` files as needed.
2. Update `DownKyi/App.axaml.cs` if the application startup or settings initialization changes.
3. Commit with a `fix:` or `chore:` message, e.g., `fix: add video quality setting`.

---

### CI Pipeline Update
**Trigger:** When changing build, packaging, or deployment logic  
**Command:** `/update-ci`

1. Edit `.github/workflows/build.yml` or related scripts.
2. Edit packaging/signing scripts as needed, such as `script/macos/package.sh`.
3. Commit with a `ci:` message, e.g., `ci: update macOS packaging script`.

---

## Testing Patterns

- **Test File Naming:**  
  Test files follow the pattern `*.test.*` (e.g., `LoginHelper.test.cs`).

- **Testing Framework:**  
  The specific framework is not detected; check existing test files for conventions.

- **Example Test File:**  
  ```csharp
  // LoginHelper.test.cs
  [TestClass]
  public class LoginHelperTests
  {
      [TestMethod]
      public void TestTokenRefresh()
      {
          // Arrange
          // Act
          // Assert
      }
  }
  ```

## Commands

| Command            | Purpose                                              |
|--------------------|------------------------------------------------------|
| /release           | Prepare and execute a new release version bump       |
| /upgrade-avalonia  | Upgrade the Avalonia UI framework version            |
| /bugfix            | Fix a bug or optimize a single feature               |
| /update-settings   | Update or optimize application settings management   |
| /update-ci         | Update CI/CD pipeline configuration or scripts       |
```
