# .NET Pack

Uses the .NET CLI `dotnet pack` [command](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-pack) to retrieve previously [build](https://github.com/codebeltnet/dotnet-build) projects and packs them into a NuGet package.

> This action is part of the Codebelt ecosystem and ensures a consistent way of: 
> 
> - Defining your CI/CD pipeline 
> - Structuring your repository
> - Keeping your codebase small and feasible
> - Writing clean and maintainable code
> - Deploying your code to different environments
> - Automating as much as possible
>
> A paved path to excel as a DevSecOps Engineer.

## Usage

To use this action in your GitHub repository, you can follow these steps:

```yaml
uses: codebeltnet/dotnet-pack@main
```

### Inputs

```yaml
with:
  # Defines the build configuration.
  configuration: 'Release'
  # The framework reference to use when retrieving the project.
  framework: 'net8.0'
  # Sets the verbosity level of the command.
  # Allowed values are e[rror], w[arn], i[nfo], d[ebug] and t[race]. 
  # The default is info.
  level: 'info'
  # Upload the created NuGet packages.
  uploadPackedArtifact: 'false'
  # The version of your project, e.g. 1.0.0.
  version:
```

### Outputs

This action has no outputs.

## Examples

### Pack and Upload for Release configuration

```yaml
- name: Pack for Release
  uses: codebeltnet/dotnet-pack@main
  with:
    configuration: Release
    uploadPackedArtifact: true
    version: ${{ needs.build.outputs.version }}
```

## Contributing to .NET Pack

Contributions are welcome! 
Feel free to submit issues, feature requests, or pull requests to help improve this action.

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
