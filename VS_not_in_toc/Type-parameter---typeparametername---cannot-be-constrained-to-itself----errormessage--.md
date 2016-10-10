---
title: "Type parameter &#39;&lt;typeparametername&gt;&#39; cannot be constrained to itself: &#39;&lt;errormessage&gt;&#39;"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a74128ae-11d0-46bf-8c0b-c7a2bf881d17
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
# Type parameter &#39;&lt;typeparametername&gt;&#39; cannot be constrained to itself: &#39;&lt;errormessage&gt;&#39;
A constraint list for a type parameter includes that same type parameter.  
  
 A constraint list on a type parameter can specify any number of interfaces and at most one class. A type argument supplied for that type parameter must implement every specified interface and inherit from the specified class. The compiler requires interfaces and classes that are already defined when it encounters a constraint list. A type parameter is not considered as a defined type until it is replaced by a suitable type argument supplied by code creating the generic type.  
  
 **Error ID:** BC32113  
  
### To correct this error  
  
1.  Check the spelling of both the type parameter and the constraints in its constraint list.  
  
2.  If there are no spelling mistakes, remove the type parameter's name from its constraint list. It cannot be constrained to itself.  
  
## See Also  
 [Generic Types in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)