---
title: "Compiler Error CS0724"
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
  - "CS0724"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0724"
ms.assetid: bcdb2017-7a43-4242-b4e2-a1ae03d6d73f
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
# Compiler Error CS0724
does not need a CLSCompliant attribute because the assembly does not have a CLSCompliant attribute  
  
 The following example generates CS0724 because of the `throw` statement inside the `finally` clause block.  
  
## Example  
 The following example generates CS0724.  
  
```  
// CS0724.cs  
using System;  
  
class X  
{  
    static void Test()  
    {  
        try  
        {  
            throw new Exception();  
        }  
        catch  
        {  
            try  
            {  
            }  
            finally  
            {  
                throw; // CS0724  
            }  
        }  
    }  
  
    static void Main()  
    {  
    }  
}  
```