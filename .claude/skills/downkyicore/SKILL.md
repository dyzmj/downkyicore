```markdown
# downkyicore Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and common workflows used in the `downkyicore` C# codebase. The repository is structured for maintainability and clarity, with a focus on modular design, conventional commit messages, and regular release and CI/CD practices. While it does not use a specific framework, it follows modern C# standards and includes workflows for versioning, dependency upgrades, settings management, bug fixing, and CI pipeline updates.

## Coding Conventions

- **File Naming:** Use PascalCase for all file names.
  - Example: `SettingsManager.Basic.cs`, `ClipboardListener.cs`
- **Import Style:** Use relative imports within the project.
  ```csharp
  using DownKyi.Core.Settings;
  using DownKyi.Services.Download;
  ```
- **Export Style:** Use named exports (public classes, interfaces, etc.).
  ```csharp
  public class SettingsManager
  {
      // ...
  }
  ```
- **Commit Messages:** Follow [Conventional Commits](https://www.conventionalcommits.org/) with these prefixes:
  - `fix:` for bug fixes
  - `chore:` for maintenance
  - `feat:` for new features
  - `refactor:` for code improvements
  - Example: `fix: correct subtitle parsing logic`

## Workflows

### Release Version Bump
**Trigger:** When preparing a new release version  
**Command:** `/release`

1. Update `CHANGELOG.md` with the latest changes.
2. Update version information in `DownKyi/Models/AppInfo.cs`.
   ```csharp
   public const string Version = "x.y.z";
   ```
3. Update `script/macos/Info.plist` with the new version.
4. Update `version.txt` with the new version number.
5. Commit changes with a message like `chore: bump version to x.y.z`.

---

### Avalonia Dependency Upgrade
**Trigger:** When upgrading Avalonia UI framework or related dependencies  
**Command:** `/upgrade-avalonia`

1. Update `Directory.Packages.props` with the new Avalonia version.
   ```xml
   <PackageVersion Include="Avalonia" Version="x.y.z" />
   ```
2. Optionally update `README.md` to reflect the new version.
3. Commit with `chore: upgrade Avalonia to x.y.z`.

---

### Settings Manager Enhancement
**Trigger:** When adding, fixing, or optimizing settings management  
**Command:** `/edit-settings`

1. Edit one or more files in `DownKyi.Core/Settings/SettingsManager.*.cs`.
2. Edit `DownKyi.Core/Settings/SettingsManager.cs` as needed.
3. Optionally update `DownKyi/App.axaml.cs` if UI changes are required.
4. Commit with `feat:` or `fix:` as appropriate.

---

### Fix Bug in Specific Feature
**Trigger:** When fixing a bug in a feature or module  
**Command:** `/bugfix`

1. Edit the relevant file(s) (e.g., `ViewModel`, `Service`, or `Utility` class).
   ```csharp
   // Example bug fix in ClipboardListener.cs
   public void OnClipboardChanged()
   {
       // Corrected logic here
   }
   ```
2. Commit with a message starting with `fix:`, e.g., `fix: handle null clipboard data`.

---

### CI Pipeline Update
**Trigger:** When updating CI/CD pipeline configuration  
**Command:** `/update-ci`

1. Edit `.github/workflows/build.yml` to change build steps or targets.
2. Edit or add scripts under `script/` (e.g., `script/macos/package.sh`).
3. Commit with `chore: update CI pipeline`.

---

## Testing Patterns

- **Test Framework:** Not explicitly detected; likely custom or standard C# test frameworks.
- **Test File Pattern:** Test files are named with `.test.` in the filename.
  - Example: `SettingsManager.test.cs`
- **Test Organization:** Tests are placed alongside or near the code they verify.
- **Writing Tests:** Follow standard C# test conventions (e.g., using `Assert`).

## Commands

| Command           | Purpose                                                       |
|-------------------|---------------------------------------------------------------|
| /release          | Prepare and bump a new release version                        |
| /upgrade-avalonia | Upgrade Avalonia UI framework and related dependencies        |
| /edit-settings    | Enhance or fix settings management logic                      |
| /bugfix           | Fix a bug in a specific feature or module                     |
| /update-ci        | Update CI/CD pipeline configuration or scripts                |
```
