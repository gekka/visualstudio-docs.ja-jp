---
title: Combos 要素 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Combos element (VSCT XML schema)
- VSCT XML schema elements, Combos
ms.assetid: ef48d2d2-0c47-4f93-8cfe-52026b6c463e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 02f0fac933ea719b712d9b3bba4117915065aa65
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49939021"
---
# <a name="combos-element"></a>Combos 要素
グループ[Combo 要素](../extensibility/combo-element.md)要素。  
  
## <a name="syntax"></a>構文  
  
```  
<Combos>  
  <Combo>... </Combo>  
  <Combo>... </Combo>  
</Combos>  
```  
  
## <a name="attributes-and-elements"></a>属性と要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|条件|任意。 参照してください[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)します。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[Combos 要素](../extensibility/combos-element.md)|複合要素をグループ化します。|  
|[Combo 要素](../extensibility/combo-element.md)|コンボ ボックスに表示されるコマンドを定義します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[Commands 要素](../extensibility/commands-element.md)|VSPackage のツールバーのコマンドのコレクションを表します。|  
  
## <a name="example"></a>例  
  
```  
<Combos>  
  <Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
    defaultWidth="100" idCommandList="cmdidGetInsertOptionsList">  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    <Strings>  
      <ButtonText>Select Insert Options</ButtonText>  
    </Strings>  
  </Combo>  
  
  <Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0500" type="DropDownCombo" defaultWidth="100"  
    idCommandList="cmdidGetInsertOptionsList">  
    <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    <Strings>  
      <ButtonText>Select Insert Options</ButtonText>  
    </Strings>  
  </Combo>  
</Combos>  
```  
  
## <a name="see-also"></a>関連項目  
 [Vspackage がユーザー インターフェイス要素を追加する方法](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [コマンド、メニューのおよびツールバー](../extensibility/internals/commands-menus-and-toolbars.md)
