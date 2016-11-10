---
title: "Compiler Error CS0263"
ms.custom: na
ms.date: 10/01/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 94fe3eb0-10e9-4602-a993-68fe125c8565
caps.latest.revision: 8
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
# Compiler Error CS0263
Partial declarations of 'type' must not specify different base classes  
  
 When defining a type in partial declarations, specify the same base types in each of the partial declarations. For more information, see [Partial Classes and Methods](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md).  
  
 The following sample generates CS0263:  
  
```  
  
// CS0263.cs  
// compile with: /target:library  
class B1  
{  
}  
  
class B2  
{  
}  
partial class C : B1  // CS0263 – is the base class B1 or B2?  
{  
}  
  
partial class C : B2  
{  
}  
```