---
title: "IDebugExceptionEvent2::PassToDebuggee"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDebugExceptionEvent2::PassToDebuggee"
helpviewer_keywords: 
  - "IDebugExceptionEvent2::PassToDebuggee"
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
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
# IDebugExceptionEvent2::PassToDebuggee
Specifies whether the exception should be passed on to the program being debugged when execution resumes, or if the exception should be discarded.  
  
## Syntax  
  
```cpp#  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```c#  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### Parameters  
 `fPass`  
 [in] Nonzero (`TRUE`) if the exception should be passed on to the program being debugged when execution resumes, or zero (`FALSE`) if the exception should be discarded.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Remarks  
 Calling this method does not actually cause any code to be executed in the program being debugged. The call is merely to set the state for the next code execution. For example, calls to the [CanPassToDebuggee](../extensibility/idebugexceptionevent2--canpasstodebuggee.md) method may return `S_OK` with the [EXCEPTION_INFO](../extensibility/exception_info.md).`dwState` field set to `EXCEPTION_STOP_SECOND_CHANCE`.  
  
 The IDE may receive the [IDebugExceptionEvent2](../extensibility/idebugexceptionevent2.md) event and call the [Continue](../extensibility/idebugprogram2--continue.md) method. The debug engine (DE) should have a default behavior to handle the case if the `PassToDebuggee` method is not called.  
  
## See Also  
 [IDebugExceptionEvent2](../extensibility/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../extensibility/idebugexceptionevent2--canpasstodebuggee.md)   
 [Continue](../extensibility/idebugprogram2--continue.md)