---
title: "Operands of type Object used in expressions for &#39;Select&#39;, &#39;Case&#39; statements; runtime errors could occur"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f11e9c9f-aa66-4eb1-8f49-abf713bef885
caps.latest.revision: 11
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
# Operands of type Object used in expressions for &#39;Select&#39;, &#39;Case&#39; statements; runtime errors could occur
A `Select`...`Case` construction uses one or more expressions of the [Object Data Type](../Topic/Object%20Data%20Type.md).  
  
 When a variable or expression evaluates to `Object`, the compiler must perform *late binding*, which causes extra operations at run time. It also exposes your application to potential run-time errors. For example, if you assign a <xref:System.Windows.Forms.Form?qualifyHint=False> to an `Object` variable and then try to compare it with a number, the runtime throws an <xref:System.InvalidCastException?qualifyHint=False> because Visual Basic cannot convert a <xref:System.Windows.Forms.Form?qualifyHint=False> object to a numeric value.  
  
 The expressions in a `Select`...`Case` construction should all be of the same data type or of closely related data types that can be converted to each other. This is because each `Case` statement compares at least one value against the test expression on which the `Select`...`Case` construction is based.  
  
 By default, this message is a warning. For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](../VS_IDE/Configuring-Warnings-in-Visual-Basic.md).  
  
 **Error ID:** BC42036  
  
### To correct this error  
  
-   If possible, arrange all the expressions to evaluate to data types for which comparison operators are defined.  
  
## See Also  
 [Select...Case Statement](../Topic/Select...Case%20Statement%20\(Visual%20Basic\).md)   
 [Arithmetic Operators in Visual Basic](../Topic/Arithmetic%20Operators%20in%20Visual%20Basic.md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)