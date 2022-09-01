---
title: NuGetInstaller@0 - NuGet Installer v0 task
description: Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# NuGetInstaller@0 - NuGet Installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Installs or restores missing NuGet packages.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# NuGet Installer v0
# Installs or restores missing NuGet packages. Use NuGetAuthenticate@0 task for latest capabilities.
- task: NuGetInstaller@0
  inputs:
    solution: '**/*.sln' # string. Required. Path to solution or packages.config. Default: '**/*.sln'.
    #nugetConfigPath: # string. Path to NuGet.config. 
    restoreMode: 'restore' # 'restore' | 'install'. Required. Installation type. Default: 'restore'.
    #noCache: false # boolean. Disable local cache. Default: false.
    #nuGetRestoreArgs: # string. NuGet arguments. 
  # Advanced
    #verbosity: '-' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: '-'.
    nuGetVersion: '3.3.0' # '3.3.0' | '3.5.0.1829' | '4.0.0.2283' | 'custom'. Required. NuGet Version. Default: '3.3.0'.
    #nuGetPath: # string. Path to NuGet.exe.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# NuGet Installer v0
# Installs or restores missing NuGet packages.
- task: NuGetInstaller@0
  inputs:
    solution: '**/*.sln' # string. Required. Path to solution or packages.config. Default: '**/*.sln'.
    #nugetConfigPath: # string. Path to NuGet.config. 
    restoreMode: 'restore' # 'restore' | 'install'. Required. Installation type. Default: 'restore'.
    #noCache: false # boolean. Disable local cache. Default: false.
    #nuGetRestoreArgs: # string. NuGet arguments. 
  # Advanced
    #verbosity: '-' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: '-'.
    nuGetVersion: '3.3.0' # '3.3.0' | '3.5.0.1829' | '4.0.0.2283' | 'custom'. Required. NuGet Version. Default: '3.3.0'.
    #nuGetPath: # string. Path to NuGet.exe.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solution"::: -->
:::moniker range="<=azure-pipelines"

**`solution`** - **Path to solution or packages.config**<br>
Type: string. Required. Default value: '**/*.sln'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the Visual Studio solution file or NuGet packages.config.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nugetConfigPath"::: -->
:::moniker range="<=azure-pipelines"

**`nugetConfigPath`** - **Path to NuGet.config**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Equivalent to the -ConfigFile NuGet.exe command line argument.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreMode"::: -->
:::moniker range="<=azure-pipelines"

**`restoreMode`** - **Installation type**<br>
Type: string. Required. Allowed values: 'restore', 'install'. Default value: 'restore'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Restore will restore the packages a solution depends upon, and is generally what you want.

Install will install packages from a packages.config file. Use this option if you want to install a standalone tool package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noCache"::: -->
:::moniker range="<=azure-pipelines"

**`noCache`** - **Disable local cache**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Equivalent to the -NoCache NuGet.exe command line argument.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetRestoreArgs"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetRestoreArgs`** - **NuGet arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to NuGet.exe restore or install. [More Information](https://docs.nuget.org/consume/command-line-reference#user-content-restore-command).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosity"::: -->
:::moniker range="<=azure-pipelines"

**`verbosity`** - **Verbosity**<br>
Type: string. Allowed values: '-', 'Quiet', 'Normal', 'Detailed'. Default value: '-'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
NuGet's verbosity level.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetVersion"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetVersion`** - **NuGet Version**<br>
Type: string. Required. Allowed values: '3.3.0', '3.5.0.1829', '4.0.0.2283', 'custom'. Default value: '3.3.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of NuGet to use, or external version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetPath"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetPath`** - **Path to NuGet.exe**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to NuGet.exe. Will override version selection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->