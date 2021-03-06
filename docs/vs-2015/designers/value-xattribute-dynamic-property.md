---
title: Value (XAttribute 動的プロパティ) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XAttribute.Value
api_type:
- Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bd9ea1fa163980a39bcd9981b9e1d757d72fcb6a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229152"
---
# <a name="value-xattribute-dynamic-property"></a>Value (XAttribute 動的プロパティ)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML 属性の値を取得または設定します。  
  
## <a name="syntax"></a>構文  
  
```  
attrib.Value   
```  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 この属性の値を表す <xref:System.String> です。  
  
## <a name="exceptions"></a>例外  
  
|例外の種類|状態|  
|--------------------|---------------|  
|<xref:System.ArgumentNullException>|設定時に `value` が `null` である場合に発生します。|  
  
## <a name="remarks"></a>Remarks  
 このプロパティは、<xref:System.Xml.Linq.XAttribute.Value%2A> クラスの <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> プロパティに相当します。ただし、この動的プロパティは変更通知もサポートします。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>   
 [XAttribute クラスの動的プロパティ](../designers/xattribute-class-dynamic-properties.md)   
 [属性](../designers/attribute-xelement-dynamic-property.md)



