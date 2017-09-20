---
title: 'CA2117: APTCA types should only extend APTCA base types | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2117
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
helpviewer_keywords:
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
- CA2117
ms.assetid: c505b586-2f1e-47cb-98ee-a5afcbeda70f
caps.latest.revision: 16
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
ms.openlocfilehash: a10a5e0fb867e819f62705a224aadb1073854a3a
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="ca2117-aptca-types-should-only-extend-aptca-base-types"></a>CA2117: APTCA types should only extend APTCA base types
|||  
|-|-|  
|TypeName|AptcaTypesShouldOnlyExtendAptcaBaseTypes|  
|CheckId|CA2117|  
|Category|Microsoft.Security|  
|Breaking Change|Breaking|  
  
## <a name="cause"></a>Cause  
 A public or protected type in an assembly with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> attribute inherits from a type declared in an assembly that does not have the attribute.  
  
## <a name="rule-description"></a>Rule Description  
 By default, public or protected types in assemblies with strong names are implicitly protected by an [Inheritance Demands](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9) for full trust. Strong-named assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute do not have this protection. The attribute disables the inheritance demand. This makes exposed types declared in the assembly inheritable by types that do not have full trust.  
  
 When the APTCA attribute is present on a fully trusted assembly, and a type in the assembly inherits from a type that does not allow partially trusted callers, a security exploit is possible. If two types `T1` and `T2` meet the following conditions, malicious callers can use the type `T1` to bypass the implicit full trust inheritance demand that protects `T2`:  
  
-   `T1` is a public type declared in a fully trusted assembly that has the APTCA attribute.  
  
-   `T1` inherits from a type `T2` outside its assembly.  
  
-   `T2`'s assembly does not have the APTCA attribute and, therefore, should not be inheritable by types in partially trusted assemblies.  
  
 A partially trusted type `X` can inherit from `T1`, which gives it access to inherited members declared in `T2`. Because `T2` does not have the APTCA attribute, its immediate derived type (`T1`) must satisfy an inheritance demand for full trust; `T1` has full trust and therefore satisfies this check. The security risk is because `X` does not participate in satisfying the inheritance demand that protects `T2` from untrusted subclassing. For this reason, types with the APTCA attribute must not extend types that do not have the attribute.  
  
 Another security issue, and perhaps a more common one, is that the derived type (`T1`) can, through programmer error, expose protected members from the type that requires full trust (`T2`). When this occurs, untrusted callers gain access to information that should be available only to fully trusted types.  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 If the type reported by the violation is in an assembly that does not require the APTCA attribute, remove it.  
  
 If the APTCA attribute is required, add an inheritance demand for full trust to the type. This protects against inheritance by untrusted types.  
  
 It is possible to fix a violation by adding the APTCA attribute to the assemblies of the base types reported by the violation. Do not do this without first conducting an intensive security review of all code in the assemblies and all code that depends on the assemblies.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 To safely suppress a warning from this rule, you must ensure that protected members exposed by your type do not directly or indirectly allow untrusted callers to access sensitive information, operations, or resources that can be used in a destructive manner.  
  
## <a name="example"></a>Example  
 The following example uses two assemblies and a test application to illustrate the security vulnerability detected by this rule. The first assembly does not have the APTCA attribute and should not be inheritable by partially trusted types (represented by `T2` in the previous discussion).  
  
 [!code-csharp[FxCop.Security.NoAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_1.cs)]  
  
## <a name="example"></a>Example  
 The second assembly, represented by `T1` in the previous discussion, is fully trusted and allows partially trusted callers.  
  
 [!code-csharp[FxCop.Security.YesAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_2.cs)]  
  
## <a name="example"></a>Example  
 The test type, represented by `X` in the previous discussion, is in a partially trusted assembly.  
  
 [!code-csharp[FxCop.Security.TestAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_3.cs)]  
  
 This example produces the following output.  
  
 **Meet at the shady glen 2/22/2003 12:00:00 AM!**  
**From Test: sunny meadow**  
**Meet at the sunny meadow 2/22/2003 12:00:00 AM!**   
## <a name="related-rules"></a>Related Rules  
 [CA2116: APTCA methods should only call APTCA methods](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)  
  
## <a name="see-also"></a>See Also  
 [Secure Coding Guidelines](/dotnet/standard/security/secure-coding-guidelines)   
 [.NET Framework Assemblies Callable by Partially Trusted Code](http://msdn.microsoft.com/en-us/a417fcd4-d3ca-4884-a308-3a1a080eac8d)   
 [Using Libraries from Partially Trusted Code](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)   
 [Inheritance Demands](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)