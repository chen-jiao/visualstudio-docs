---
title: "Suspend request is pending"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30947"
  - "bc30947"
helpviewer_keywords: 
  - "BC30947"
ms.assetid: 6bc4df1b-e833-47c7-9568-9ced67a2af5d
caps.latest.revision: 8
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Suspend request is pending
In the Visual Studio debugger, an expression specifies a procedure call, but there is a request to suspend the thread.  
  
 The debugger does not attempt to call a procedure on a thread that is not active.  
  
 **Error ID:** BC30947  
  
### To correct this error  
  
-   If possible, determine the source of the request to suspend the thread, so you can prevent it from happening again.  
  
-   Terminate and restart debugging.  
  
## See Also  
 [Debugging in Visual Studio](../debugger/debugging-in-visual-studio.md)   
 [How to: Start Execution](assetId:///b0fe0ce5-900e-421f-a4c6-aa44ddae453c)   
 [How to: Stop Debugging or Stop Execution](assetId:///03c68f95-aa96-481b-990e-467e065453a5)   
 [Code Stepping Overview](assetId:///8791dac9-64d1-4bb9-b59e-8d59af1833f9)   
 [Expressions in Visual Basic](../Topic/Expressions%20in%20Visual%20Basic.md)