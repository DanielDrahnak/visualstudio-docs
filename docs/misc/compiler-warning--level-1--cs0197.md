---
title: "Compiler Warning (level 1) CS0197"
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
  - "CS0197"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0197"
ms.assetid: 2b5b1b8d-ce13-4bd7-b80a-abb80e9f79ad
caps.latest.revision: 17
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
# Compiler Warning (level 1) CS0197
Passing 'argument' as ref or out or taking its address may cause a runtime exception because it is a field of a marshal-by-reference class  
  
 Any class that derives, directly or indirectly, from \<xref:System.MarshalByRefObject> is a marshal-by-reference class. Such a class can be marshaled by reference across process and machine boundaries. Thus, instances of this class could be proxies to remote objects. You cannot pass a field of a proxy object as [ref](../Topic/ref%20\(C%23%20Reference\).md) or [out](../Topic/out%20\(C%23%20Reference\).md). So, you cannot pass fields of such a class as `ref` or `out`, unless the instance is [this](../Topic/this%20\(C%23%20Reference\).md), which can not be a proxy object.  
  
## Example  
 The following sample generates CS0197.  
  
```  
// CS0197.cs  
// compile with: /W:1  
class X : System.MarshalByRefObject  
{  
   public int i;  
}  
  
class M  
{  
   public int i;  
   static void AddSeventeen(ref int i)  
   {  
      i += 17;  
   }  
  
   static void Main()  
   {  
      X x = new X();  
      x.i = 12;  
      AddSeventeen(ref x.i);   // CS0197  
  
      // OK  
      M m = new M();  
      m.i = 12;  
      AddSeventeen(ref m.i);  
   }  
}  
```