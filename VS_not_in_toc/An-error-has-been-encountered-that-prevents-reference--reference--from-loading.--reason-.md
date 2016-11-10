---
title: "An error has been encountered that prevents reference &#39;reference&#39; from loading. &lt;reason&gt;"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0e922611-197b-4607-bc31-03f80bd3e7e1
caps.latest.revision: 7
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# An error has been encountered that prevents reference &#39;reference&#39; from loading. &lt;reason&gt;
A fatal error has been encountered when removing a reference from the project file. The causes for this error are identified in <reason\>, and could be:  
  
-   Malformed GUID for a reference. This is applicable for COM references only.  
  
-   Bad wrapper tool. Currently, the wrapper tool property can be one of tlbimp, aximp, or primary. This is applicable for COM references only.  
  
-   Bad project reference string. This is applicable for project-to-project references only.  
  
 **To correct this error**  
  
-   Add the reference to the project to resolve this error.  
  
     Any reference for which this diagnostic is displayed will not be loaded into the project.  
  
## See Also  
 [NIB: Project Properties (Visual Studio)](assetId:///eb4c97ed-f667-4850-98d0-6e2a4d21bbca)