## Review Checklist

### 1. Frends Task Project File

- Path: `Frends.*/Frends.*/*.csproj`
- [ ] Contains required fields:
    - [ ] `<TargetFramework>net8.0</TargetFramework>`
    - [ ] `<Version>x.0.0</Version>`
    - [ ] `<Authors>Frends</Authors>`
    - [ ] `<PackageLicenseExpression>MIT</PackageLicenseExpression>`
    - [ ] `<GenerateDocumentationFile>true</GenerateDocumentationFile>`
    - [ ] `<Description>`
    - [ ] 
      `<RepositoryUrl>https://github.com/FrendsPlatform/Frends.SYSTEM/tree/main/Frends.SYSTEM.ACTION</RepositoryUrl>`
    - [ ] `<Nullable>disable</Nullable>`
- [ ] Contains required package references:
    - [ ] `StyleCop.Analyzers v1.2.0-beta.556`
    - [ ] `FrendsTaskAnalyzers v1.*`
- [ ] Contains required files:
    - [ ] `<Content Include="migration.json" PackagePath="/" Pack="true"/>`
    - [ ] `<Content Include="../CHANGELOG.md" PackagePath="/" Pack="true"/>`
    - [ ] `<AdditionalFiles Include="FrendsTaskMetadata.json" PackagePath="/" Pack="true"/>`
- [ ] Auto formatting applied

### 2. Frends Task Test Project File

- Path: `Frends.*/Frends.*.Tests/*.Tests.csproj`
- [ ] Contains required fields:
    - [ ] `<TargetFramework>net8.0</TargetFramework>`
    - [ ] `<IsPackable>false</IsPackable>`
    - [ ] `<Nullable>disable</Nullable>`
- [ ] Contains required package references:
    - [ ] `StyleCop.Analyzers v1.2.0-beta.556`
- [ ] Auto formatting applied

### 3. Additional Files

- [ ] Present: `Frends.*/LICENSE`
- [ ] Present: `Frends.*/README.md`
    - [ ] Contains badges (build, license, coverage)
    - [ ] Includes developer setup instructions
    - [ ] Includes test setup instructions
    - [ ] Does not include parameter descriptions
- [ ] Present: `Frends.*/CHANGELOG.md`
    - [ ] Includes all functional changes
    - [ ] Indicates breaking changes with upgrade notes
    - [ ] Avoids non-functional notes like "refactored xyz"
- [ ] Present: `Frends.*/Frends.*/FrendsTaskMetadata.json`
    - [ ] Contains task method reference `Frends.System.Action.System.Action`
- [ ] Present: `Frends.*/Frends.*/migration.json`
    - [ ] Contains breaking change migration information for Frends if breaking changes exist
- [ ] StyleCop.Analyzers suppression files added and setup:
  - [ ] Present: `Frends.*/Frends.*/GlobalSuppressions.cs`
  - [ ] Present: `Frends.*/Frends.*.Tests/GlobalSuppressions.cs`
  - [ ] Follows standards from Frends Task Template
- [ ] Present: `.gitignore`
  - [ ] Includes `.idea/` folders
- [ ] Present: `Frends.*/.gitignore`
  - [ ] Includes `.idea/` folders
- [ ] Auto formatting applied

### 4. Source Code

- [ ] Solution builds
- [ ] File-scoped namespace applied
- [ ] Usings placed before the namespace
- [ ] Unused code is removed
- [ ] Warnings resolved (if possible)
- [ ] Follows Microsoft C# code conventions
- [ ] Typos and grammar mistakes resolved
- [ ] Auto formatting applied

### 5. GitHub Actions Workflows

- Path: `.github/workflows/*.yml`
- [ ] Task has required workflow files:
    - [ ] `*_release.yml`
      - [ ] contains secret `feed_api_key: ${{ secrets.TASKS_FEED_API_KEY }}`
    - [ ] `*_test_on_main.yml`
      - [ ] contains secret `badge_service_api_key: ${{ secrets.BADGE_SERVICE_API_KEY }}`
    - [ ] `*_test_on_push.yml`
      - [ ] contains secret `badge_service_api_key: ${{ secrets.BADGE_SERVICE_API_KEY }}`
      - [ ] contains secret `test_feed_api_key: ${{ secrets.TASKS_TEST_FEED_API_KEY }}`
- [ ] default permissions set for `GITHUB_TOKEN`
- [ ] `workdir: Frends.SYSTEM.ACTION`
- [ ] `strict_analyzers: true`
- [ ] `dotnet_version: 8.0.x`
- [ ] Docker setup included if task depends on external system (`prebuild_command: docker-compose up -d`)