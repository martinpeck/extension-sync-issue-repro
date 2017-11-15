# Repro for `func extensions install`/`sync` issue

This project generates the following MSBuild error when `func extensions install` was originally run, and each time that `func extensions sync` is run.

From my own debugging, it's the `sync` stage that fails. The `install` stage appears to work fine.

The error generated is:

```
error : Metadata generation failed. [/Users/martinpeck/dev/extension-sync-issue-repro/functions-extensions/extensions.csproj]
```

The repro steps were:

1 - create a folder
2 - `cd` into folder
3 - `func init`
4 - `func function new` and create a new JS function taking defaults
5 - `func extensions install --package Microsoft.Azure.WebJobs.Extensions.CosmosDB --version 3.0.0-beta5` though it doesn't matter which extension you install...any will do

Observe that the error above is generated

6 - `func extensions sync`

Observer that the error above is generated