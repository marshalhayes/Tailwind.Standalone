# Tailwind.Standalone

Use the Tailwind Standalone CLI the right way.

## Getting Started

1. Install the package

    ```shell
    dotnet add package MarshalHayes.Tailwind.Standalone
    ```

2. Configure the properties in your `.csproj` file

    ```csproj
    <PropertyGroup>
        <TailwindVersion>latest</TailwindVersion>
        <TailwindInputStyleSheetPath>Styles/main.css</TailwindInputStyleSheetPath>
        <TailwindOutputStyleSheetPath>wwwroot/main.css</TailwindOutputStyleSheetPath>
    </PropertyGroup>
    ```

## How it works

This package declares custom MSBuild targets that download the Tailwind Standalone CLI and run it against your project during `dotnet build`.
You just have to specify the Tailwind version, and the input & output stylesheet paths.

## Available Options

- `TailwindVersion`: The version of the Tailwind Standalone CLI to download.
- `TailwindDownloadPath`: The path to where to download the Tailwind Standalone CLI. This property is optional, and defaults to `%LOCALAPPDATA%` on Windows, and `$XDG_CACHE_HOME` on Linux and MacOS.
- `TailwindInputStyleSheetPath`: The path to the input stylesheet.
- `TailwindOutputStyleSheetPath`: The path to the output stylesheet.
- `TailwindOptimizeOutputStyleSheet`: Whether to optimize the output stylesheet. This property is optional, and defaults to false.
- `TailwindMinifyOutputStyleSheet`: Whether to minify the output stylesheet. This property is optional, and defaults to false when Configuration is Debug, and true when Configuration is Release.
- `TailwindGenerateSourceMap`: Whether to generate a source map for the output stylesheet. This property is optional, and defaults to true when Configuration is Debug, and false when Configuration is Release.
- `TailwindOutputSourceMapPath`: The path to where to write the generated source map file. This property is optional, and when not specified, inline source maps are generated. Requires TailwindGenerateSourceMap to be true.
- `TailwindDownloadUrl`: The URL to the Tailwind Standalone CLI. This property is optional, and defaults to downloading the specified version from GitHub.
