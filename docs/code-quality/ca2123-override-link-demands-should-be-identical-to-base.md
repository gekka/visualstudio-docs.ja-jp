---
title: 'CA2123: Override link demands should be identical to base | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
manager: wpickett
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: b5ec358a3f42e8b82240e901cdad6a5201c41e7a
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Override link demands should be identical to base
|||  
|-|-|  
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|  
|CheckId|CA2123|  
|Category|Microsoft.Security|  
|Breaking Change|Breaking|  
  
## <a name="cause"></a>Cause  
 A public or protected method in a public type overrides a method or implements an interface, and does not have the same [Link Demands](/dotnet/framework/misc/link-demands) as the interface or virtual method.  
  
## <a name="rule-description"></a>Rule Description  
 This rule matches a method to its base method, which is either an interface or a virtual method in another type, and then compares the link demands on each. A violation is reported if either the method or the base method has a link demand and the other does not.  
  
 If this rule is violated, a malicious caller can bypass the link demand merely by calling the unsecured method.  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 To fix a violation of this rule, apply the same link demand to the overide method or implementation. If this is not possible, mark the method with a full demand or remove the attribute altogether.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 Do not suppress a warning from this rule.  
  
## <a name="example"></a>Example  
 The following example shows various violations of this rule.  
  
 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]  
  
## <a name="see-also"></a>See Also  
 [Secure Coding Guidelines](/dotnet/standard/security/secure-coding-guidelines)   
 [Link Demands](/dotnet/framework/misc/link-demands)