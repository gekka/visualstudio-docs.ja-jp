---
title: AssignProjectConfiguration タスク | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57e513dc8b5cb914fd26f23b63e1a7e7d4908b76
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290512"
---
# <a name="assignprojectconfiguration-task"></a>AssignProjectConfiguration タスク
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
このタスクは、構成文字列の一覧を受け入れ、それらを指定されたプロジェクトに割り当てます。  
  
## <a name="task-parameters"></a>タスク パラメーター  
 `AssignProjectConfiguration` タスクのパラメーターの説明を次の表に示します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`SolutionConfigurationContents`|省略可能な `string` 型の出力パラメーターです。<br /><br /> 各プロジェクトのプロジェクト構成を含む XML 文字列が含まれます。 構成は、指定したプロジェクトに割り当てられます。|  
|`DefaultToVcxPlatformMapping`|省略可能な `string` 型の出力パラメーターです。<br /><br /> ほとんどのタイプで使用されるプラットフォーム名から .vcxproj ファイルで使用される<br /><br /> プラットフォーム名へのマッピングのセミコロン区切りのリストが含まれます。<br /><br /> 例えば:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|  
|`VcxToDefaultPlatformMapping`|Optional<br /><br /> `string` 出力パラメーターです。<br /><br /> .vcxproj プラットフォーム名からほとんどのタイプで使用されるプラットフォーム名へのマッピングのセミコロン区切りのリストが含まれます。<br /><br /> 例えば:<br /><br /> `"Win32=AnyCPU;X64=X64"`|  
|`CurrentProjectConfiguration`|省略可能な `string` 型の出力パラメーターです。<br /><br /> 現在のプロジェクトの構成が含まれます。|  
|`CurrentProjectPlatform`|省略可能な `string` 型の出力パラメーターです。<br /><br /> 現在のプロジェクトのプラットフォームが含まれます。|  
|`OnlyReferenceAndBuildProjectsEnabledInSolutionConfiguration`|省略可能な `bool` 型の出力パラメーターです。<br /><br /> プロジェクト構成で無効になっている場合でも、参照を構築する必要があることを示すフラグが含まれます。|  
|`ShouldUnsetParentConfigurationAndPlatform`|省略可能な `bool` 型の出力パラメーターです。<br /><br /> 親の構成およびプラットフォームの設定を解除する必要があるかどうかを示すフラグが含まれます。|  
|`OutputType`|省略可能な `string` 型の出力パラメーターです。<br /><br /> プロジェクトの出力の種類が含まれます。|  
|`ResolveConfigurationPlatformUsingMappings`|省略可能な `bool` 型の出力パラメーターです。<br /><br /> 渡されたプロジェクト参照の構成およびプラットフォームを解決するためにビルドで既定のマッピングを使用する必要があるかどうかを示すフラグが含まれます。|  
|`AssignedProjects`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型の出力パラメーターです。<br /><br /> 解決済み参照パスのリストが含まれます。|  
|`UnassignedProjects`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型の出力パラメーターです。<br /><br /> 出力の事前解決リストを使用して解決できなかったプロジェクト参照項目のリストが含まれます。|  
  
## <a name="remarks"></a>Remarks  
 上記のパラメーター以外に、このタスクは <xref:Microsoft.Build.Tasks.TaskExtension> クラスからパラメーターを継承します。このクラス自体は、<xref:Microsoft.Build.Utilities.Task> クラスから継承されます。 これらの追加のパラメーターの一覧とその説明については、「 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [タスク](../msbuild/msbuild-tasks.md)   
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)



