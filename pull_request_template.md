[]# Frends Task Pull Request

## Summary
<!-- Brief description of changes -->

## Review Checklist

### 1. Frends Task Project Files
- Path: `Frends.*/Frends.*/*.csproj`
- [ ] Targets .NET 8
- [ ] Uses MIT license (`<PackageLicenseExpression>MIT</PackageLicenseExpression>`)
- [ ] Contains required fields:
  - [ ] `<Version>`
  - [ ] `<Authors>Frends</Authors>`
  - [ ] `<Description>`
  - [ ] `<RepositoryUrl>`
  - [ ] `<GenerateDocumentationFile>true</GenerateDocumentationFile>`

### 2. File: FrendsTaskMetadata.json
- [ ] Present: `Frends.*/Frends.*/FrendsTaskMetadata.json`
- [ ] FrendsTaskMetadata.json contains correct task method reference
- [ ] FrendsTaskMetadata.json is included in the project nuget package with path = "/"

### 3. File: README.md
- [ ] Present: `Frends.*/README.md`
- [ ] Contains badges (build, license, coverage)
- [ ] Includes developer setup instructions
- [ ] Does not include parameter descriptions

### 4. File: CHANGELOG.md
- [ ] Present: `Frends.*/CHANGELOG.md`
- [ ] Includes all functional changes
- [ ] Indicates breaking changes with upgrade notes
- [ ] Avoids non-functional notes like "refactored xyz"
- [ ] CHANGELOG.md is included in the project nuget package with path = "/"

### 5. File: migration.json
- [ ] Present: `Frends.*/Frends.*/migration.json`
- [ ] Contains breaking change migration information for Frends, if breaking changes exist
- [ ] migration.json is included in the project nuget package with path = "/"

### 6. Source Code Documentation
- Path: `Frends.*/Frends.*/*.cs`
- [ ] Every public method and class has:
  - [ ] `<summary>` XML comments
  - [ ] `<example>` XML comments
  - [ ] Optionally `<frendsdocs>` XML comments, if needed
- [ ] Follows Microsoft C# code conventions
- [ ] Uses semantic task result documentation (Success, Error, Data)

### 7. GitHub Actions Workflows
- Path: `.github/workflows/*.yml`
- [ ] Task has required workflow files:
  - [ ] `*_test.yml`
  - [ ] `*_main.yml`
  - [ ] `*_release.yml`
- [ ] Correct workdir pointing to task folder
- [ ] Docker setup included if task depends on external system (docker-compose.yml)

### 8. Task Result Object Structure
- Path: `Frends.*/Frends.*/*.cs`
- [ ] Category attribute is present, if applicable
- [ ] All task result classes include:
  - [ ] `Success` (bool)
  - [ ] Task-specific return value (e.g., Data, FilePaths), if needed
  - [ ] Error object with Message and AdditionalInfo
- [ ] Result structure is flat and simple
- [ ] Does not use 3rd-party types
- [ ] Uses dynamic JToken only when structure is unknown


---

## Additional Notes
<!-- Any additional information for reviewers -->
