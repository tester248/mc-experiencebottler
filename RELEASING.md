# Creating a Release

This repository uses GitHub Actions to automatically build and publish releases.

## Automatic Release Process

When you push a tag starting with `v`, the release workflow will automatically:

1. Build the mod with Gradle
2. Create a GitHub Release
3. Upload the JAR files to the release

## Steps to Create a Release

1. **Update version in `gradle.properties`:**
   ```properties
   mod_version=1.21.4+build.1
   ```

2. **Update `CHANGELOG.md`** with the new version and changes

3. **Commit your changes:**
   ```bash
   git add gradle.properties CHANGELOG.md
   git commit -m "Prepare version X.X.X"
   ```

4. **Create and push a tag:**
   ```bash
   git tag -a vX.X.X -m "Release version X.X.X"
   git push origin vX.X.X
   ```

5. **GitHub Actions will automatically:**
   - Build the project
   - Create a release on GitHub
   - Upload the JAR files

## Example

```bash
# For version 1.21.4+build.1
git tag -a v1.21.4+build.1 -m "Release 1.21.4+build.1"
git push origin v1.21.4+build.1
```

## Viewing Releases

- Releases: https://github.com/tester248/mc-experiencebottler/releases
- Actions: https://github.com/tester248/mc-experiencebottler/actions

## Build Status

Every push and pull request triggers a build workflow that:
- Compiles the mod
- Runs tests
- Uploads build artifacts

Check the Actions tab to see build status and download development builds.
