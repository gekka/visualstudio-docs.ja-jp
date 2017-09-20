---
title: 'CA2114: Method security should be a superset of type | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: 17
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
ms.openlocfilehash: 0c39c591401550442414c301d076f08d77796b6f
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: Method security should be a superset of type
|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|Category|Microsoft.Security|  
|Breaking Change|Breaking|  
  
## <a name="cause"></a>Cause  
 A type has declarative security and one of its methods has declarative security for the same security action, and the security action is not [Link Demands](/dotnet/framework/misc/link-demands) or [Inheritance Demands](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9), and the permissions checked by the type are not a subset of the permissions checked by the method.  
  
## <a name="rule-description"></a>Rule Description  
 A method should not have both a method-level and type-level declarative security for the same action. The two checks are not combined; only the method-level demand is applied. For example, if a type demands permission `X`, and one of its methods demands permission `Y`, code does not have to have permission `X` to execute the method.  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 Review your code to make sure that both actions are required. If both actions are required, make sure that the method-level action includes the security specified at the type level. For example, if your type demands permission `X`, and its method must also demand permission `Y`, the method should explicitly demand `X` and `Y`.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 It is safe to suppress a warning from this rule if the method does not require the security specified by the type. However, this is not an ordinary scenario and might indicate a need for a careful design review.  
  
## <a name="example"></a>Example  
 The following example uses environment permissions to demonstrate the dangers of violating this rule. In this example, the application code creates an instance of the secured type before denying the permission required by the type. In a real-world threat scenario, the application would require another way to obtain an instance of the object.  
  
 In the following example, the library demands write permission for a type and read permission for a method.  
  
 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## <a name="example"></a>Example  
 The following application code demonstrates the vulnerability of the library by calling the method even though it does not meet the type-level security requirement.  
  
 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 This example produces the following output.  
  
 **[All permissions] Personal information: 6/16/1964 12:00:00 AM**  
**[No write permission (demanded by type)] Personal information: 6/16/1964 12:00:00 AM**  
**[No read permission (demanded by method)] Could not access personal information: Request failed.**   
## <a name="see-also"></a>See Also  
 [Secure Coding Guidelines](/dotnet/standard/security/secure-coding-guidelines)   
 [Inheritance Demands](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [Link Demands](/dotnet/framework/misc/link-demands)   
 [Data and Modeling](/dotnet/framework/data/index)