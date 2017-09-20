---
title: "MergeLocalizationDirectives タスク | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
caps.latest.revision: 5
author: kempb
ms.author: kempb
manager: ghogen
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3d32d11a430227800cb3ed53831a9565eb6adeb3
ms.openlocfilehash: e56ad5826bd6d18bd4409e98f8d54c49d266af82
ms.contentlocale: ja-jp
ms.lasthandoff: 05/30/2017

---
# <a name="mergelocalizationdirectives-task"></a>MergeLocalizationDirectives タスク
<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> タスクは、1 つ以上の [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式ファイルのローカリゼーション属性とコメントを、アセンブリ全体で単一のファイルにマージします。  
  
## <a name="task-parameters"></a>タスク パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`GeneratedLocalizationFiles`|必須の **ITaskItem[]** 型のパラメーターです。<br /><br /> [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式の個々のファイルに対するローカリゼーション ディレクティブ ファイルの一覧を指定します。|  
|`OutputFile`|省略可能な **String** 型の出力パラメーターです。<br /><br /> コンパイルされたローカリゼーション ディレクティブ アセンブリの出力パスを指定します。|  
  
## <a name="remarks"></a>コメント  
 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] のコンテンツには、ローカリゼーション属性とコメントを追加できます。 [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)] のローカリゼーション サポートを使用すると、ローカリゼーション属性とコメントを取り出し、生成されるアセンブリとは別の .loc ファイルに格納できます。 これを行うには、**LocalizationPropertyStorage** 属性を使用します。 ローカリゼーション属性とコメント、および **LocalizationPropertyStorage** の詳細については、「[ローカリゼーション属性とコメント](/dotnet/framework/wpf/advanced/localization-attributes-and-comments)」を参照してください。  
  
## <a name="example"></a>例  
 いくつかの [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式ファイルのローカリゼーション コメントを単一の .loc ファイルにマージする方法を次の例に示します。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>関連項目  
 [WPF MSBuild リファレンス](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference (タスク リファレンス)](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild リファレンス](../msbuild/msbuild-reference.md)   
 [タスク リファレンス](../msbuild/msbuild-task-reference.md)   
 [WPF アプリケーション (WPF) のビルド](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)