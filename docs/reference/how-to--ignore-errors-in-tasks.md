---
title: "How to: Ignore Errors in Tasks"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, ignoring errors"
  - "ContinueOnError attribute [MSBuild]"
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
caps.latest.revision: 17
ms.author: "kempb"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# How to: Ignore Errors in Tasks
Sometimes you want a build to be tolerant of faults in certain tasks. If those non-critical tasks fail, you want the build to continue because it can still produce the required output. For example, if a project uses a `SendMail` task to send an e-mail message after each component is built, you might consider it acceptable for the build to proceed to completion even when the mail servers are unavailable and the status messages cannot be sent. Or, for example, if intermediate files are usually deleted during the build, you might consider it acceptable for the build to proceed to completion even when those files cannot be deleted.  
  
## Using the ContinueOnError Attribute  
 The `ContinueOnError` attribute of the `Task` element controls whether a build stops or continues when a task failure occurs. This attribute also controls whether errors are treated as errors or warnings when the build continues.  
  
 The `ContinueOnError` attribute can contain one of the following values:  
  
-   **WarnAndContinue** or **true**. When a task fails, subsequent tasks in the [Target](../reference/target-element--msbuild-.md) element and the build continue to execute, and all errors from the task are treated as warnings.  
  
-   **ErrorAndContinue**. When a task fails, subsequent tasks in the `Target` element and the build continue to execute, and all errors from the task are treated as errors.  
  
-   **ErrorAndStop** or **false** (default). When a task fails, the remaining tasks in the `Target` element and the build aren't executed, and the entire `Target` element and the build is considered to have failed.  
  
 Versions of the .NET Framework before 4.5 supported only the `true` and `false` values.  
  
 The default value of `ContinueOnError` is `ErrorAndStop`. If you set the attribute to `ErrorAndStop`, you make the behavior explicit to anyone who reads the project file.  
  
#### To ignore an error in a task  
  
-   Use the `ContinueOnError` attribute of the task. For example:  
  
     `<Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>`  
  
## Example  
 The following code example illustrates that the `Build` target still runs and the build is considered a success, even if the `Delete` task fails.  
  
```  
<Project DefaultTargets="FakeBuild"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Files Include="*.obj"/>  
    </ItemGroup>  
    <Target Name="Clean">  
        <Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>  
    </Target>  
  
    <Target Name="FakeBuild" DependsOnTargets="Clean">  
        <Message Text="Building after cleaning..."/>  
    </Target>  
</Project>  
```  
  
## See Also  
 [Task Reference](../reference/msbuild-task-reference.md)   
 [Tasks](../reference/msbuild-tasks.md)